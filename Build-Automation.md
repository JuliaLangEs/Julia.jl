**Build automation software, continuous integration (CI), continuous delivery (CD), Infrastructure management, Packaging, Release engineering/ management tools, Software configuration management (SCM) software...**

+ [INSTALL](#install)
+ [PACKAGING](#packaging)
   + [Containers](#containers)
   + [DistrOS](#distros)
+ [BACKPORTS](#backports)
+ [BUILD AUTOMATION](#build-automation)
+ [CONTINUOUS INTEGRATION](#continuous-integration)
   + [Org-Julia-CI](#org-julia-ci)
   + [Git-Hooks](#git-hooks)
+ [DEVELOPMENT](#development)
+ [NEWS](#news)
+ [Virtualization](#virtualization)

----

# INSTALL 
+ [Download and install Julia on various Operating Systems](http://julialang.org/downloads/)
+ List of [Julia Modules](http://docs.julialang.org/en/latest/manual/modules/).
+ [The Julia Standard Library](http://docs.julialang.org/en/latest/stdlib/)
+ Julia [Sample programs](https://github.com/JuliaLang/julia/tree/master/examples)


----

# PACKAGING
+ [METADATA.jl](https://github.com/JuliaLang/METADATA.jl) :: The official set of Julia packages.
   + [MetadataTools.jl](https://github.com/IainNZ/MetadataTools.jl) :: Functionality to analyze the structure of Julia's METADATA repository.
+ [BinDeps.jl](https://github.com/JuliaLang/BinDeps.jl) :: Tool for building binary dependencies for Julia modules.
+ [Compat.jl](https://github.com/JuliaLang/Compat.jl) :: A package for cross-version compatibility between Julia v0.3 and v0.4 - takes care of syntax breakage and provides compatibility constructs that will work in both versions without warnings.       
+ [DeclarativePackages.jl](https://github.com/rened/DeclarativePackages.jl) :: (jdp for short), allows the project to declaratively specify which Julia packages are being used, with exact version or commit details.
+ [PackageEvaluator.jl](https://github.com/IainNZ/PackageEvaluator.jl) :: The Julia package evaluator.
+ [PkgUtils.jl](https://github.com/johnmyleswhite/PkgUtils.jl) :: Tools for analyzing Julia packages.
+ Getting Julia to build on [PowerPC under Linux](https://github.com/JuliaLang/julia/blob/master/Make.powerpc).
+ [Require.jl](https://github.com/jkroso/Require.jl) :: A better module system for Julia.
+ [Requires.jl](https://github.com/one-more-minute/Requires.jl) :: A Julia package that will quickly load your package dependencies.
+ [RPMmd.jl](https://github.com/ihnorton/RPMmd.jl) :: is a front-end installer for RPM-md packages and a fork of WinRPM.jl.
+ [WinRPM.jl](https://github.com/JuliaLang/WinRPM.jl) :: RPM-md processing library - WinRPM is an installer for RPM packages provided by an RPM-md build system.

### Package/Infrastructure management tools and Documentation 
   - Official [Julia Package list](http://docs.julialang.org/en/latest/packages/packagelist/).
   - The [Julia package manager manual](http://docs.julialang.org/en/latest/manual/packages/)
   - [packages.julialang.org](https://github.com/IainNZ/packages.julialang.org) :: Concept for a next-gen package listing.
   - [cache.julialang.org](https://github.com/staticfloat/cache.julialang.org) :: Super-simple bottle-caching infrastructure for the site.
   - [Package Development Documentation](http://docs.julialang.org/en/latest/manual/packages/#package-development)   

##### DOCS
   - The [Julia package manager manual](http://docs.julialang.org/en/latest/manual/packages/)
   - Official [Julia Package list](http://pkg.julialang.org/).
   - [METADATA.jl](https://github.com/JuliaLang/METADATA.jl) :: The official set of Julia packages.
   - [MetadataTools.jl](https://github.com/IainNZ/MetadataTools.jl) :: Functionality to analyze the structure of Julia's METADATA repository.
   - [Package Development Documentation](http://docs.julialang.org/en/latest/manual/packages/#package-development)


## Containers
+ [Docker](https://registry.hub.docker.com/_/julia/) image for Julia.
+ [julia-vagrant](https://github.com/staticfloat/julia-vagrant) :: Packer/Vagrant script recipes for making virtual machines (VM's) - create Vagrant boxes and Openstack images for performing builds and tests of Julia.

## DistrOS
+ [Julia Ecosystem Status](http://status.julialang.org/) :: Track the status of various parts of the Julia language ecosystem; from nightly binary builds of Julia to automated testing of packages.
+ [julia-buildbot](https://github.com/staticfloat/julia-buildbot) :: Buildbot configuration for build.julialang.org. It is written in Python and is listed by virtue of being a tool used within the Julia ecosystem.

#### Binaries
__Pre-compiled Binaries__
+ [Julia-0.3.9 for Linux 64-bit](https://julialang.s3.amazonaws.com/bin/linux/x64/0.3/julia-0.3.9-linux-x86_64.tar.gz), as a gzipped tar ball. 
+ Build an executable binary with [this script](https://github.com/JuliaLang/julia/blob/master/contrib/build_executable.jl)

#### Debian-Ubuntu
+ [APT.jl](https://github.com/bbshortcut/APT.jl) :: A module to manipulate Debian Advanced Package Tool (APT). It comes with `pnlt`, an executable that allows to manage package name lists.
+ [DebbyPacker.jl](https://github.com/UCL/DebbyPacker.jl) :: Set of scripts to "easily" create debian packages.
+ [Julia-Debian](https://github.com/staticfloat/julia-debian) :: Elliot Saba (@staticfloat) packages [nightlies](https://launchpad.net/~staticfloat/+archive/ubuntu/juliareleases), consisting of a repo with just the packaging metadata, that gets used by a repo with [automated buildscripts](https://github.com/staticfloat/julia-nightly-packaging). It is highly recommended to use the Julia [PPA releases](https://launchpad.net/~staticfloat/+archive/ubuntu/juliareleases) if you are having build problems with Julia on Debian-Ubuntu systems. In a terminal, type the following commands:

```
    sudo add-apt-repository ppa:staticfloat/juliareleases
    sudo add-apt-repository ppa:staticfloat/julia-deps
    sudo add-apt-repository ppa:staticfloat/julianightlies
    sudo apt-get update && sudo apt-get upgrade
    sudo apt-get install julia
```

__NotaBene__: The PPA `julianightlies` will pull the `master` (unstable) branch from github, so if you are not interested in the unstable bleeding-edge version of JULIA, stick to the stable release versions that are usually tagged as `vX.X` branches.

#### Fedora-RHEL
+ Fedora :: Milan Bouchet-Valat (@nalimilan on github) maintains the builds for [Fedora 19 and 20](http://nalimilan.perso.neuf.fr/transfert/), a mirror is also available from the [Fedoraprojet](http://copr-be.cloud.fedoraproject.org/results/nalimilan/julia/) site.

----

# BACKPORTS
+ [Julia-Backports](https://groups.google.com/forum/#!forum/julia-backports) Mailing list.

----

# BUILD AUTOMATION
+ [Jake.jl](https://github.com/nolta/Jake.jl) :: Rake for Julia.
+ [Juke.jl](https://github.com/kshramt/Juke.jl) :: `make` in Julia.
+ [OpenStack.jl](https://github.com/loladiro/OpenStack.jl)

----

# CONTINUOUS INTEGRATION
+ Merge your Julia code with mainline to test it on a [Travis-CI build server](https://travis-ci.org/JuliaLang/).

## Org-[Julia-CI](https://github.com/julia-ci)
+ [TravisTest.jl](https://github.com/JuliaCI/TravisTest.jl) :: Repository for testing Julia support at the Travis Continuous Integration (CI) service.

### Git-Hooks
+ [julia-helper](https://github.com/jiahao/julia-helper) :: Scripts to help Julia developers.

----

# DEVELOPMENT
Helper tools for core `julia` language development.
+ [HackThatBase.jl](https://github.com/ihnorton/HackThatBase.jl) :: A helper tool to reload and test modifications to base without recompiling the full system image.

----

# NEWS
+ [Devops Weekly](http://www.devopsweekly.com/)

----

# [Virtualization](http://en.wikipedia.org/wiki/Category:Virtualization_software)
+ [Ansible and Docker](https://developer.rackspace.com/blog/ansible-and-docker/)
+ [RudeOil.jl](https://github.com/UCL/RudeOil.jl) :: A package to easily interact with docker and docker-machine.
