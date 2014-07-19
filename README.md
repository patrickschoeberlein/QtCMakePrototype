QtCMakePrototype
================

a starting point for simple Qt projects with CMake. The CMakeLists.txt file follows the Qt CMake Manual at http://qt-project.org/doc/qt-5/cmake-manual.html#using-qt-5-with-cmake-older-than-2-8-9 

Qt itself is not included, download prebuilt version at http://qt-project.org/downloads

to built Qt with MinGW see https://qt-project.org/wiki/Building_Qt_Desktop_for_Windows_with_MinGW

if CMake does not find the Qt library, it probably needs an additional path (Qt5Widgets_DIR, easiest way would be using CMake GUI) - e.g. for the prebuilt MinGW+OpenGL version from qt-project.org the path should look like C:\Qt\Qt5.3.1\5.3\mingw482_32\lib\cmake\Qt5Widgets

the CMakeLists.txt does currently not care about copying DLLs to bin folder, also there is no explicit binary folder...
