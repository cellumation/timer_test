cmake_minimum_required(VERSION 3.22)
project(timer_test)

find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)

add_executable(${PROJECT_NAME} src/main.cpp)
target_link_libraries(${PROJECT_NAME} PRIVATE rclcpp::rclcpp)
target_compile_options(${PROJECT_NAME} PRIVATE -Wall -Wextra -Werror)

install(TARGETS ${PROJECT_NAME} RUNTIME DESTINATION lib/${PROJECT_NAME})
install(DIRECTORY launch DESTINATION share/${PROJECT_NAME})
install(FILES params.yaml DESTINATION share/${PROJECT_NAME})

ament_package()
