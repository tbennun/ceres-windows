ceres-windows
=============

A ceres-solver wrapper for Visual Studio.
Written and tested on Visual Studio 2010 and 2012, using Win32/x64 on both Debug and Release.

For a wrapper that uses ceres-solver 1.9.0 and CXSparse, go to the
CXSparse branch at https://github.com/tbennun/ceres-windows/tree/cxsparse

Conversion to VS2012 should be done automatically by Visual Studio. If not, modify the platform toolset
to VS2012 in the project properties. Conversion to VS2013 and above should be performed in the 
same manner.


Sample projects (using ceres-solver's code examples) are also embedded in the solution.

Dependencies
============

  * Eigen (http://eigen.tuxfamily.org/): Version 3.2 or above. It's a header-only 
    library, so just extract Eigen to the solution directory and it should compile. 
    Alternatively, set it up in one of your default include directories.

Libraries
=========

  * ceres-solver 1.11.0: http://ceres-solver.org/

  * Google glog: http://www.github.com/google/glog


License
=======

The license of this wrapper is the same as ceres-solver and glog, New BSD license.
