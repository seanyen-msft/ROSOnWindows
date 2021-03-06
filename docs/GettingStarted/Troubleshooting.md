# Troubleshooting ROS for Windows
The team is monitoring [ROS Answers](https://answers.ros.org/questions/) 🔗, [ROS Discourse](https://discourse.ros.org/) 🔗, and the [/r/ROS Subreddit](http://reddit.com/r/ros) 🔗.

> This page will be updated with environment related problems as we diagnose them with customers.

# Windows Specific Bugs
Please create a GitHub issue on the [ROS on Windows GitHub repository](https://github.com/ms-iot/ROSOnWindows) 🔗.

# No Visual Studio command line build?
If you find that you do not have a Visual Studio command line in your start menu, it likely means that it wasn't installed during Visual Studio setup. 

To Fix, please launch the Visual Studio installer and select to install the C++ build environment.

# CMake Fails to find Visual Studio after upgrade
CMake caches part of the build environment when building a workspace. If you upgrade Visual Studio after building, you may encounter an error like this:

```
CMake Error in CMakeLists.txt:
  The CMAKE_CXX_COMPILER:

    C:/Program Files (x86)/Microsoft Visual Studio/2019/Community/VC/Tools/MSVC/14.22.27905/bin/Hostx64/x64/cl.exe
```

To correct this situation, please delete the devel, build and install directories and rebuild:

```bat
cd c:\catkin_ws
rd /s build devel install
```
