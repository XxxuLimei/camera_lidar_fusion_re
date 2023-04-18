# camera_lidar_fusion_re  
## 0418：  
1. catkin_make的时候遇到好多错误，以下是比较有用的参考链接：  
- [error: ‘CV_LOAD_IMAGE_UNCHANGED’ was not declared in this scope](https://blog.csdn.net/weixin_44675820/article/details/124796674)  
- [ROS使用自定义全局路径规划器编译时报错 ‘xxx’ is not a member of ‘pcl::traits’的解决方法](https://blog.csdn.net/qq_44339029/article/details/123751466)  
- [关于opencv报错：未定义标识符"CV_WINDOW_AUTOSIZE"](https://blog.csdn.net/weixin_44312186/article/details/89000922)  
- [【Debug】error: ‘format’ is not a member of ‘boost’](https://blog.csdn.net/xingdou520/article/details/84861434)  
- [error: ‘CV_WINDOW_NORMAL’ was not declared in this scope](https://blog.csdn.net/weixin_43848456/article/details/123380782)  
- [error: no matching function for call to ‘_IplImage::_IplImage(cv::Mat&)’](https://blog.csdn.net/weixin_41855010/article/details/111402710?ydreferer=aHR0cHM6Ly93d3cuZ29vZ2xlLmNvbS8%3D)  

上面这个问题，应该在编译的时候换成`catkin_make -DCMAKE_BUILD_TYPE=Release -DCMAKE_CXX_FLAGS=-DCV__ENABLE_C_API_CTORS`  
2. 还剩一个error:`error: #error "OpenCV 4.x+ requires enabled C++11 support"`实在是没有找到有效的解决办法。  
3. 过程：  
- 新建`catkin_workspace`，cd进入后新建`src`文件夹，把`Camera-Lidar-Fusion-ROS`package放进去  
- 返回`catkin_workspace`文件夹下，在该路径的终端上`catkin_make -DCMAKE_BUILD_TYPE=Release -DCMAKE_CXX_FLAGS=-DCV__ENABLE_C_API_CTORS`  
