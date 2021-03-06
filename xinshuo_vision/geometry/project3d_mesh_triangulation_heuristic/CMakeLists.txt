cmake_minimum_required(VERSION 3.7)
project(project3d_mesh_triangulation_heuristic)

message(STATUS "start running cmake...")

include_directories(/home/xinshuo/include/pcl-1.8)
include_directories(/home/xinshuo/include/eigen3)
include_directories(/home/xinshuo/include)
include_directories(/opt/VTK-7.0.0/include/vtk-7.0)
include_directories(/usr/include)
include_directories(/home/xinshuo/lib/xinshuo_toolbox)

link_directories(/usr/local/lib)
link_directories(/usr/lib/x86_64-linux-gnu)
link_directories(/opt/VTK-7.0.0/lib)
link_directories(/home/xinshuo/Qt5.7.0/5.7/gcc_64/lib)

# with visualization
#file(GLOB LIBS "/home/xinshuo/lib/xinshuo_toolbox/xinshuo_visualization/mesh*.cpp" "/home/xinshuo/lib/xinshuo_toolbox/xinshuo_vision/geometry/*.cpp" "/home/xinshuo/lib/xinshuo_toolbox/xinshuo_io/*.cpp" "/home/xinshuo/lib/xinshuo_toolbox/xinshuo_miscellaneous/type_conversion.cpp" "/home/xinshuo/lib/xinshuo_toolbox/xinshuo_miscellaneous/debug_tool.cpp" "/home/xinshuo/lib/xinshuo_toolbox/xinshuo_math/*.cpp")

# without visualization
file(GLOB LIBS "/home/xinshuo/lib/xinshuo_toolbox/xinshuo_vision/geometry/*.cpp" "/home/xinshuo/lib/xinshuo_toolbox/xinshuo_io/*.cpp" "/home/xinshuo/lib/xinshuo_toolbox/xinshuo_miscellaneous/type_conversion.cpp" "/home/xinshuo/lib/xinshuo_toolbox/xinshuo_miscellaneous/debug_tool.cpp" "/home/xinshuo/lib/xinshuo_toolbox/xinshuo_math/*.cpp")

set(CMAKE_CXX_STANDARD 11)
#set(LIBSs computer_vision/geometry/camera_geometry.cpp)
#set(SOURCE_FILES main.cpp camera_geometry.cpp IdDataParser.cpp mycamera.cpp MyMesh.cpp pts_2d_conf.cpp pts_3d_conf.cpp pts_on_mesh.cpp type_conversion.cpp pts_2d_tool.cpp math_functions.cpp debug_tool.cpp)
#set(SOURCE_FILES test_mesh_visualization.cpp mesh_visualization.cpp camera_geometry.cpp IdDataParser.cpp mycamera.cpp MyMesh.cpp pts_2d_conf.cpp pts_3d_conf.cpp pts_on_mesh.cpp type_conversion.cpp pts_2d_tool.cpp math_functions.cpp debug_tool.cpp)
set(SOURCE_FILES main.cpp)
add_executable(project3d_mesh_triangulation_heuristic ${SOURCE_FILES} ${LIBS})

# with visualization
#target_link_libraries(project3d_mesh_triangulation_heuristic libvtkCommonCore-7.0.so libQt5Gui.so.5 libvtkCommonMath-7.0.so libvtkRenderingCore-7.0.so libvtkCommonDataModel-7.0.so libpcl_visualization.so libboost_system.so libboost_thread.so libopencv_core.so libopencv_calib3d.so libopencv_imgproc.so libpcl_kdtree.so libpcl_common.so libpcl_io.so)

# without visualization
target_link_libraries(project3d_mesh_triangulation_heuristic libboost_system.so libboost_thread.so libopencv_core.so libopencv_calib3d.so libopencv_imgproc.so libpcl_kdtree.so libpcl_common.so libpcl_io.so)
