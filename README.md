Delaunay Utility Plugin
=======================

About
-----

This project is a 3ds Max plugin written in C++ that gives the user the ability to compute 2D and 3D [Delaunay triangulation](https://en.wikipedia.org/wiki/Delaunay_triangulation) (through MAXScript interface). Both triangulation algorithms take a set of 2D (3D) points as an input. The 2D (3D) triangulation covers the convex hull of this set with triangles (tetrahedrons). To achieve the triangulation the [Bowyer-Watson](https://en.wikipedia.org/wiki/Bowyer%E2%80%93Watson_algorithm) algorithm is used.


![2d example](example2D.png)

Building the project
--------------------

The project must be built using Visual Studio that has VS2015 (v140) compiler and tools installed. Before opening the project in VS, check the `DelaunayUtilityPlugin.vcxproj` and `DelaunayUtilityPlugin.vcxproj.user` and make sure that the paths to 3ds Max executable and SDK are correct with respect to your system setup.

Note: The project uses the Eigen linear algebra open source library. For some reason compiling Eigen in 3ds Max plugin project might cause this unexpected error in Eigen source code:

`packages\eigen.3.3.3\build\native\include\eigen\src\core\util\memory.h(275): error C4701: potentially uninitialized local variable 'i' used`

This can be corrected by changing the line 267 in `Memory.h` from `std::size_t i;` to `std::size_t i = 0;`.


Documentation
-------------

Documentation can be easily generated by Doxygen. Just run it in the root directory that contains the `Doxyfile`.


Example scene
-------------

The `example_scene` directory contains an example 3ds Max scene that showcases how the plugin works. It also contains a textfile containing the MAXScript commands used to generate the scene. This can be used to understand the MAXScript interface of the plugin.


Binaries
--------

The compiled DLLs for 3ds Max 2017 & 2018 can be found in `generated_binaries` folder. 


Author
------

Created by Jeysym in 2018.

License
-------

This project is licensed under MIT licnse (see LICENSE file).
