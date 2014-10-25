ceres-windows
=============

A ceres-solver + CXSparse wrapper for Visual Studio.
Written and tested on Visual Studio 2010 and 2012, using Win32/x64 on both Debug and Release.
Conversion to VS2013 and above should be straightforward (done by modifying the solution file).

Sample projects (using ceres-solver's code examples) are also embedded in the solution.

Libraries
=========

-ceres-solver: http://ceres-solver.org/
-CXSparse: http://www.cise.ufl.edu/research/sparse/CXSparse/
-Google glog: https://code.google.com/p/google-glog/

Dependencies
============

-Eigen (http://eigen.tuxfamily.org/): Tested with v3.2.2. It's a header-only 
 library, so just extract Eigen to the solution directory and it should compile. 
 Alternatively, set it up in one of your default include directories.

License
=======

The license of this wrapper is the same as ceres-solver and glog, New BSD license.
Note that CXSparse is distributed under the GNU LGPL license.
