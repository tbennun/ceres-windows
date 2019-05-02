ceres-windows
=============

A ceres-solver wrapper for Visual Studio.
Tested on Visual Studio 2010, 2012 and 2015, using Win32/x64 on both Debug and Release.

For a wrapper that uses ceres-solver 1.9.0 and CXSparse, go to the
CXSparse branch at https://github.com/tbennun/ceres-windows/tree/cxsparse

Conversion to newer versions of Visual Studio should be performed automatically by the IDE. 
If projects are not compiling, make sure that the platform toolset matches the version of Visual
Studio in the project properties.


Sample projects (using ceres-solver's code examples) are also embedded in the solution.

How to clone with submodules
============

This repository contains git submodules. In order to clone it appropriately the submodules need to be initialized

```shell
git clone https://github.com/tbennun/ceres-windows.git
cd ceres-windows
git submodule update --init --recursive
```

Static Linkage
=========
If an external project is statically linked to ceres-solver, the following settings have to be modified in the linked project.
In Project properties->C/C++->General->Preprocessor Definitions, add the following flags:
```shell
%(PreprocessorDefinitions);GOOGLE_GLOG_DLL_DECL=;_MBCS;CERES_MSVC_USE_UNDERSCORE_PREFIXED_BESSEL_FUNCTIONS
```
To add the include and library folders, first create an environment variable that points to the folder you cloned this repository into, e.g., `CERES_WINDOWS_DIR=c:\ceres-windows`.

In Project properties->C/C++->General->Additional Include Directories, add:
```shell
;$(CERES_WINDOWS_DIR)\ceres-solver\include
```
In Project properties->Linker->General->Additional Library Directories, add:
```shell
;$(CERES_WINDOWS_DIR)\$(Platform)\$(Configuration)
```

Make sure you compile ceres-solver for each platform and configuration you intend to use (x64/Release etc.).

Finally, in Project properties->Linker->Input->Additional Dependencies, add:
```shell
;ceres.lib;libglog_static.lib
```


Dependencies
============

  * Eigen (http://eigen.tuxfamily.org/): Version 3.3 or above. It's a header-only 
    library, so simply extract Eigen to the solution directory and it should compile. 
    Alternatively, set it up in one of your default include directories.

Libraries
=========

  * ceres-solver 1.12.0: http://ceres-solver.org/

  * Google glog: http://www.github.com/google/glog


License
=======

The license of this wrapper is the same as ceres-solver and glog, New BSD license.
