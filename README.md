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

Importing
=========
You will need to add Project properties->C/C++->General->Pre Processor Definitions as follows, once completed they should look like this in Visual Studio:
```code
GOOGLE_GLOG_DLL_DECL=;_MBCS;%(PreprocessorDefinitions)
```
Add the include and lib folders, first create an environment variable that points to the folder you cloned this repository into.

eg CERES_WINDOWS_DIR=c:\ceres-windows

Project properties->C/C++->General->Additional Include Directories, add
```code
;$(CERES_WINDOWS_DIR)\ceres-solver\include
```
Project properties->Linker->General->Additional Lirary Directories, add
    ;$(CERES_WINDOWS_DIR)\$(Platform)\$(Configuration)

Make sure you compile for each platform and configuration you intend to use, eg x64 / Release.

Project properties->Linker->Input->Additional Dependencies, add
```code
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
