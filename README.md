# A Guide to SemVer
Quickly and easily learn all of the rules of semver.  I created this document due to the lack of legible and concise documentation about semver, and to erase all ambiguity.  This document is targeted for Rust programmers, but it could be adapted to other languages too.

# Start a project
When you initially start a project and give it a name and now need a version, consider four cases:
- I don't have working code, but code that does nothing, and I  want to share: give it version `v0.0.0`
- I have something that partially works: give it version `v0.0.1`
- I have working code, but there's still work to be done: give it version `v0.1.0`
- I have working code, and it works perfectly, I'll probably never change: give it version `v1.0.0`

----------

# v0.0.0
This means there's no code, just ideas.  The version shall not be incremented until code has been written.

# v0.0.Z
Once you have code, and it's in an extremely experimental state, you can go to version `v0.0.1`.  You may skip this if your code could possibly be useful and usable by someone else (it's OK if it's still experimental) and release `v0.1.0`.

For code in this state, increment `z` for each release no matter what, no extra thinking necessary.

----------

# v0.Y.Z
`v0.1.0` marks the first experimental release that could possibly be usable and useful by others.

## When do I increment Y?
- New public `struct`s, `enum`s (or new variants), `union`s, `trait`s, `type`s, `fn`s or anything public added inside of an `impl`. (You can get around this with feature-gating or target-gating).
- Removal of public `struct`s, `enum`s (or new variants), `union`s, `trait`s, `type`s, `fn`s or anything public added inside of an `impl`.
- Rename of public `struct`s, `enum`s (or new variants), `union`s, `trait`s, `type`s, `fn`s or anything public added inside of an `impl`.

## When do I increment Z?
- Bug fix.
- Support for a new target platform.
- New feature that makes available new public `struct`s, `enum`s (or new variants), `union`s, `trait`s, `type`s, `fn`s or anything public added inside of an `impl`.  This is called **feature-gating**.
- New platform-specific public `struct`s, `enum`s (or new variants), `union`s, `trait`s, `type`s, `fn`s or anything public added inside of an `impl` for a target platform that wasn't supported in the previous version.  This is called **target-gating**.

----------

# vX.Y.Z
`v1.0.0` marks the first stable release of the project.  This is when your project is considered more or less "finished" (although software is never really finished).

## When do I increment X?
- Removal of public `struct`s, `enum`s (or new variants), `union`s, `trait`s, `type`s, `fn`s or anything public added inside of an `impl`.
- Rename of public `struct`s, `enum`s (or new variants), `union`s, `trait`s, `type`s, `fn`s or anything public added inside of an `impl`.

## When do I increment Y?
- New public `struct`s, `enum`s (or new variants), `union`s, `trait`s, `type`s, `fn`s or anything public added inside of an `impl`. (You can get around this with feature-gating or target-gating).
- Mark function you don't want to be used anymore as *"deprecated"* (absolutely do **not** label *depreciated*).

## When do I increment Z?
- Bug fix.
- Support for a new target platform.
- New feature that makes available new public `struct`s, `enum`s (or new variants), `union`s, `trait`s, `type`s, `fn`s or anything public added inside of an `impl`.  This is called **feature-gating**.
- New platform-specific public `struct`s, `enum`s (or new variants), `union`s, `trait`s, `type`s, `fn`s or anything public added inside of an `impl` for a target platform that wasn't supported in the previous version.  This is called **target-gating**.
