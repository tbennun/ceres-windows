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
