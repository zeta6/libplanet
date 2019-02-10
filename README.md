Libplanet
=========

[![Build Status](https://travis-ci.com/planetarium/libplanet.net.svg?branch=master)][Travis CI]
[![Codecov](https://codecov.io/gh/planetarium/libplanet.net/branch/master/graph/badge.svg)][Codecov]
[![NuGet](https://img.shields.io/nuget/v/Libplanet.svg?style=flat)][NuGet]
[![NuGet (prerelease)](https://img.shields.io/nuget/vpre/Libplanet.svg?style=flat)][NuGet]

Libplanet is a .NET library for creating multiplayer online game in
decentralized fashion, which means the whole gameplay occurs on a
peer-to-peer network among equal nodes rather than an authorized central
server.  Under the hood, it incorporates many features (e.g.,
[digital signature], [BFT] consensus, data replication) of a [blockchain].

[Travis CI]: https://travis-ci.com/planetarium/libplanet.net
[Codecov]: https://codecov.io/gh/planetarium/libplanet.net
[NuGet]: https://www.nuget.org/packages/Libplanet/
[digital signature]: https://en.wikipedia.org/wiki/Digital_signature
[BFT]: https://en.wikipedia.org/wiki/Byzantine_fault_tolerance
[blockchain]: https://en.wikipedia.org/wiki/Blockchain


NuGet
-----

Although this project has never released any version, for everyday and every
merge commit, it is packed into a *.nupkg* and uploaded to [NuGet] with
a hyphen-suffixed version name.

For a merge commit build, a version name is like `0.1.0-dev.123+20181231` where
`123` is a build number in our CI system and `20181231` is a date of the build.
For a daily build, a version name is like `0.1.0-nightly.20181231`.

In the near future, we are going to submit it to [Unity Asset Store] too.

[Unity Asset Store]: https://assetstore.unity.com/


Build
-----

The following command installs dependencies (required library packages) and
builds the whole Libplanet solution:

~~~~~~~~ bash
msbuild /r
~~~~~~~~

Note that `msbuild` is distributed together with Mono framework or
Visual Studio.


Test
----

To build and run unit tests at a time execute the below command:

~~~~~~~~ bash
msbuild /r /t:'Build;XunitTest' Libplanet.Tests
~~~~~~~~

It's okay to omit `/r` and `Build` task if you've already run `msbuild /r`
right before:

~~~~~~~~ bash
msbuild /t:XunitTest Libplanet.Tests
~~~~~~~~
