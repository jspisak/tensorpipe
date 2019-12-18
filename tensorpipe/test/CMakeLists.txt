add_subdirectory(common)
add_subdirectory(util/ringbuffer)
add_subdirectory(util/shm)

add_executable(tensorpipe_test
  ${CMAKE_CURRENT_SOURCE_DIR}/transport/uv/loop_test.cc
  )
target_link_libraries(tensorpipe_test tensorpipe_uv)
target_link_libraries(tensorpipe_test gtest_main)

enable_testing()
add_test(tensorpipe_test tensorpipe_test)