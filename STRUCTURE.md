# Structure and organization of security bindings

## Introduction

## Goals and motivations

## Structure

### Cesque level

This is the 'lower' level of the bindings. It is designed to serve as a thin
layer over C, consisting only of `foreign import` bindings, any necessary setup
to ensure that users do not have to deal with C linkage or bundling issues, and
documentation of use.

Specifically, the following principles apply:

* Users of these libraries should never have to even think about how the
  libraries are bundled or linked to. Any and all handling of this, for any
  platform, must be done by the library.
* These libraries cannot have any dependencies other than `base`.
* Modules can only contain `foreign import` declarations.
* The documentation for the modules must be strong enough to stand alone:
  specifically, at least 80% of all questions regarding the use of bindings must
  be answerable entirely from the documentation of the module, _not_ the library
  it wraps or binds to.
* CI must check that the wrapping or bundling works correctly. This must
  include checks on Windows: this is _especially_ important, as this is the most
  problematic platform.

### Haskelly level

This is the 'higher' level of the bindings, broadly divided into two categories:

* The 'algorithmic' category, where the focus is on providing a familiar
  interface to the libraries providing this functionality; and
* The 'functional' category, where the focus is on performing some task,
  regardless of what algorithms get used there.

An example of a package in the 'algorithmic' category, consider the package
`cryptography-argon2`, which would provide a set of wrappers around familiar
Haskell functionality, allowing it to be used in a Haskell project which
requires Argon2 (for whatever reason) without having to deal with C, the FFI, or
anything similar. An example of a package in the 'functional' category, consider
the package `cryptography-password-hashing`, which embodies good practices for
password hashing, allowing Haskell projects to handle this task easily, without
necessarily needing to understand precisely how this gets done.

Both of the examples would use the Cesque `cryptography-libsodium` for
implementations: the differences are their focus and the APIs they expose. For
'algorithmic' category packages, the focus is on providing easy and secure use
of an _algorithm_ in Haskell, without considering use case; for 'functional'
category packages, the focus is on providing an easy and secure way to _do some
task_, without focus on the algorithm or algorithms chosen to do so.

These packages, unlike the Cesque layer, are expected to provide more
abstraction, both to avoid the complexities of C and the FFI, but also to
address various expectations that Haskellers have, regarding things such as:

* No unnecessary use of `IO` (even if this is by way of 'safe' `unsafePerformIO`
  use);
* Implementation of standard, law-abiding type classes, such as `Eq`, in a
  correct and secure way;
* Wrappers around raw `ForeignPtr`s for data that is meant to be passed around,
  or generated in a very specific way.

Specifically, the following principles generally apply:

* These libraries cannot depend on non-boot packages;
* Abstraction should be kept minimal. `newtype`-wrapping a `ForeignPtr` is fine,
  type class hierarchies without laws are not.
* Whenever possible, if there are multiple secure ways to do something, without
  a definite 'this one is always better' option, users of these libraries should
  be given _all_ options, as well as a detailed explanation of why they should
  prefer any given one.
* Partiality must not exist unless specifically marked as unsafe, through a
  dedicated `Unsafe` module or prefixing the name with `unsafe`. This extends to
  instances of known partial type classes (such as `Read`).

These principles apply to 'algorithmic' category packages specifically:

* The packages should document as much as possible that is known about the
  algorithm, providing relevant links for detail where it would be too hard to
  include.
* The typical _secure_ uses should be enumerated.
* Any caveats to performance should be documented clearly.
* 'The algorithm is the focus': abstractions should only be done to hide the use
  of C FFI, or where the abstraction is both obvious and unarguable. Use cases
  should not be pre-supposed.

These principles apply to 'functional' category packages specifically:

* 'The task is the focus': specifics regarding algorithms or implementations
  should only factor into the abstractions if there really is no other way.
* There should be one, and only one, correct way to perform the task the package
  is designed for. If there are legitimately multiple right ways to do
  something, their differences must be _clearly_ enumerated and marked, with a
  focus on non-security-familiar users.
* Doing the right thing should be easy; doing the wrong thing should be
  impossible.

## Organization

### What gets bindings and wrappers?

Given infinite time, there are quite a few possible bindings and wrappers we
_could_ define: however, given finite time and labour, some standards for
inclusion and effort must be put down. In our case, given any possible thing we
could work on, it must fit the following criteria to be considered, in the
following order:

1. Is this a good practice in the current year regarding security?
2. Is there genuine need from some person or organization in the ecosystem and
   community for this?

We prioritize security over demand for several reasons. Firstly, one of the core
foci of this organization and project is the improvement of security-related
practices in the Haskell ecosystem. By implementing functionality that is known
to be insecure or a bad practice, we are implicitly stating that this is OK,
which works directly counter to a stated goal. Secondly, 
