
if (UNIX)
else(UNIX)
link_directories(${PROJECT_SOURCE_DIR}/vsprojects/bin/${CMAKE_BUILD_TYPE}/
                 ${LIBRARY_OUTPUT_PATH}/${CMAKE_BUILD_TYPE}/
                 ${PROJECT_SOURCE_DIR}/3rdparty/glog-0.3.4/${CMAKE_BUILD_TYPE})
endif(UNIX)

add_executable(benchmark_fd_channel_vs_pipe_event_watcher fd_channel_vs_pipe_event_watcher.cc)
if (UNIX)
target_link_libraries(benchmark_fd_channel_vs_pipe_event_watcher evpp_static event glog pthread)
else(UNIX)
target_link_libraries(benchmark_fd_channel_vs_pipe_event_watcher evpp_static event libglog_static)
endif(UNIX)


