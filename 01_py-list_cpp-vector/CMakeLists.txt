cmake_minimum_required(VERSION 2.8.12)
project(example)


# 查找Python和pybind11依赖
#  pip install "pybind11[global]" 
find_package(pybind11 REQUIRED)


# 设置C++标准为C++11（覆盖pybind11默认的C++14）
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# 添加优化和警告选项
add_compile_options(-O3 -Wall -fPIC)

# 创建Python模块
pybind11_add_module(example example.cpp)
