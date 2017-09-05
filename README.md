## Project name: sai2-common-lite (version: 0.1.0)
Note: This project uses Semantic Versioning (http://semver.org/).

### Project description:
The Sai2-Common-Lite library implements a set of simplifying interfaces and helper modules to create robot control applications. Sai2-Common-Lite is the 'lite' version of the Sai2-Common library. It does not have the simulation module and can run on Windows. 

* __parser__ module: to load a robot and world state specification from xml
* __model__ module: creating articulated rigid body models to represent the robots, 
* __graphics__ module: rendering the world graphically

### 3rdParty dependencies (* = installation required):

* Redis*: Redis server [brew, apt-get]
* Hiredis*: Redis minimalist client [brew, apt-get]
* JsonCpp*: JSON serialization [brew, apt-get]
* Eigen3*: Linear algebra [brew, apt-get]
* TinyXML2*: XML parser [brew, apt-get]
* GLFW3*: Window management [brew, apt-get]
* Chai3d: Graphics and haptics [https://github.com/chai3d/chai3d]
* RBDL: Articulated rigid-body kinematics, forward dynamics and inverse dynamics. [https://bitbucket.org/rbdl/rbdl/src]  
Note: Please specify the following CMake flags when building RBDL to build the URDF reader addon: 
``` cmake
cmake -DRBDL_BUILD_ADDON_URDFREADER=ON -DRBDL_USE_ROS_URDF_LIBRARY=OFF ..
```

### SAI library dependencies:
* 


### Installation instructions:
-- Windows:
* set EIGEN_INCLUDE_DIR  
* set TINY_INCLUDE_DIR 
* set RBDL_INCLUDE_DIR
* set RBDL_LIBRARIES
* set RBDL_URDFREADER_LIBRARIES 


--> NOTE: 


# if the installed or the using project don't have CMAKE_SIZEOF_VOID_P set, ignore it:
if("${CMAKE_SIZEOF_VOID_P}" STREQUAL "" OR "8" STREQUAL "")
   return()
endif()

# check that the installed version has the same 32/64bit-ness as the one which is currently searching:
if(NOT CMAKE_SIZEOF_VOID_P STREQUAL "8")
  math(EXPR installedBits "8 * 8")
  set(PACKAGE_VERSION "${PACKAGE_VERSION} (${installedBits}bit)")
  set(PACKAGE_VERSION_UNSUITABLE TRUE)
endif()

-- OSX/ Linux:

1. mkdir build
2. cmake ..
3. make

### Uninstallation instructions: 
-- OSX/ Linux:

1. rm -r build
2. rm -r ~/.cmake/packages/SAI2-COMMON-LITE

### Getting started:
Take a look at sample applications under examples/.
You can run them from build/examples/<x-example>/.

### License:
Currently pending licensing. PLEASE DO NOT DISTRIBUTE.

### Project contributors:
* Gerald Brantner
* Brian Soe
* Mikael Jorda
* Shameek Ganguly
* Toki Migimatsu

### For questions, contact:
manips.sai@gmail.com  
mjorda@stanford.edu  
shameekg@stanford.edu
