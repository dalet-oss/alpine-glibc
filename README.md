## alpine-glibc-packager

Stores (in Git LFS), and builds when necessary, Alpine glibc packages.

Derived from a combination of:

-  https://github.com/sgerrand/alpine-pkg-glibc
-  https://github.com/sgerrand/docker-glibc-builder
-  https://github.com/sgerrand/docker-alpine-abuild


## Why is the directory tree the way it is?

... to fill in...

##  Maintainers: adding a new glibc version

- Edit [glibc-versions.yml](glibc-versions.yml) to add an entry for the new glibc version, with dummy checksum.
- Push this change to `master`.
- Github Actions will compile the new glibc version, and commit it and its updated checksum.
- After this has completed, you should *manually* trigger both the `compile-glibc` and `package-apks` workflows,
  because Github Actions explicitly prevents recursive workflow triggering (for understandable reasons!)
