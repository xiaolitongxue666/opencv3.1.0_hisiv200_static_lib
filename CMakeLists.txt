cmake_minimum_required(VERSION 2.8.0)
project(opencv_hisi_test)

SET(CMAKE_SYSTEM_NAME Linux)
SET(CMAKE_C_COMPILER "arm-hisiv200-linux-gcc")
SET(CMAKE_CXX_COMPILER "arm-hisiv200-linux-g++")

## Bring the headers, into the project
include_directories(/home/xiaoli/Code/OpenCV/3.1.0/install/include)
include_directories(/home/xiaoli/Code/OpenCV/3.1.0/install/include/opencv)
include_directories(/home/xiaoli/Code/OpenCV/3.1.0/install/include/opencv2)

## Add libs
link_directories(/home/xiaoli/Code/OpenCV/3.1.0/install/lib)
link_directories(/home/xiaoli/Code/OpenCV/3.1.0/install/share/OpenCV/3rdparty/lib)

set(SOURCE_FILES
        src/opencv_test.cpp
	)

add_executable(opencv_hisi_test ${SOURCE_FILES})

target_link_libraries(opencv_hisi_test -Wl,--start-group

 libopencv_stitching.a 
 libopencv_superres.a 
 libopencv_videostab.a 
 libopencv_photo.a 
 libopencv_aruco.a 
 libopencv_bgsegm.a 
 libopencv_bioinspired.a
 libopencv_dnn.a 
 libopencv_dpm.a 
 libopencv_fuzzy.a 
 libopencv_line_descriptor.a 
 libopencv_optflow.a 
 libopencv_plot.a 
 libopencv_reg.a 
 libopencv_saliency.a 
 libopencv_stereo.a 
 libopencv_structured_light.a 
 libopencv_rgbd.a 
 libopencv_surface_matching.a 
 libopencv_tracking.a 
 libopencv_datasets.a 
 libopencv_text.a 
 libopencv_face.a 
 libopencv_xfeatures2d.a 
 libopencv_shape.a 
 libopencv_video.a 
 libopencv_ximgproc.a 
 libopencv_calib3d.a 
 libopencv_features2d.a 
 libopencv_flann.a 
 libopencv_xobjdetect.a 
 libopencv_objdetect.a 
 libopencv_highgui.a 
 libopencv_videoio.a 
 libopencv_imgcodecs.a 
 libopencv_ml.a 
 libopencv_imgproc.a 
 libopencv_core.a

 libzlib.a
 liblibjpeg.a
 liblibwebp.a
 liblibpng.a
 liblibjasper.a
 liblibprotobuf.a 

 stdc++
 dl
 m
 pthread
 rt

 -Wl,--end-group)





