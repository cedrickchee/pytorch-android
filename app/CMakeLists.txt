cmake_minimum_required(VERSION 3.4.1)

add_library(
             native-lib
             SHARED
             src/main/cpp/native-lib.cpp
             )
find_library(
          android-lib
          android
          )

include(AndroidNdkModules)
android_ndk_import_module_cpufeatures()

add_library(
    caffe2
    STATIC
    IMPORTED
    )
set_target_properties(
    caffe2
    PROPERTIES IMPORTED_LOCATION
    ${CMAKE_CURRENT_LIST_DIR}/src/main/jniLibs/${ANDROID_ABI}/libcaffe2.a
    )
add_library(
        caffe2_detectron_ops
        SHARED
        IMPORTED
)
set_target_properties(
        caffe2_detectron_ops
        PROPERTIES IMPORTED_LOCATION
        ${CMAKE_CURRENT_LIST_DIR}/src/main/jniLibs/${ANDROID_ABI}/libcaffe2_detectron_ops.so
)

add_library(
    c10
    STATIC
    IMPORTED
    )
set_target_properties(
        c10
        PROPERTIES IMPORTED_LOCATION
        ${CMAKE_CURRENT_LIST_DIR}/src/main/jniLibs/${ANDROID_ABI}/libc10.a
)
add_library(
    thread_pool
    STATIC
    IMPORTED
    )
set_target_properties(
    thread_pool
    PROPERTIES IMPORTED_LOCATION
    ${CMAKE_CURRENT_LIST_DIR}/src/main/jniLibs/${ANDROID_ABI}/libpthreadpool.a
    )
add_library(
    clog
    STATIC
    IMPORTED
    )
set_target_properties(
    clog
    PROPERTIES IMPORTED_LOCATION
    ${CMAKE_CURRENT_LIST_DIR}/src/main/jniLibs/${ANDROID_ABI}/libclog.a
    )

add_library(
    protobuf
    STATIC
    IMPORTED
    )
set_target_properties(
    protobuf
    PROPERTIES IMPORTED_LOCATION
    ${CMAKE_CURRENT_LIST_DIR}/src/main/jniLibs/${ANDROID_ABI}/libprotobuf.a
    )
add_library(
        caffe2_protos
        STATIC
        IMPORTED
)
set_target_properties(
        caffe2_protos
        PROPERTIES IMPORTED_LOCATION
        ${CMAKE_CURRENT_LIST_DIR}/src/main/jniLibs/${ANDROID_ABI}/libcaffe2_protos.a
)
add_library(
        onnx
        STATIC
        IMPORTED
)
set_target_properties(
        onnx
        PROPERTIES IMPORTED_LOCATION
        ${CMAKE_CURRENT_LIST_DIR}/src/main/jniLibs/${ANDROID_ABI}/libonnx.a
)
add_library(
        onnx_proto
        STATIC
        IMPORTED
)
set_target_properties(
        onnx_proto
        PROPERTIES IMPORTED_LOCATION
        ${CMAKE_CURRENT_LIST_DIR}/src/main/jniLibs/${ANDROID_ABI}/libonnx_proto.a
)
add_library(
        onnxifi_dummy
        SHARED
        IMPORTED
)
set_target_properties(
        onnxifi_dummy
        PROPERTIES IMPORTED_LOCATION
        ${CMAKE_CURRENT_LIST_DIR}/src/main/jniLibs/${ANDROID_ABI}/libonnxifi_dummy.so
)
add_library(
        onnxifi_loader
        STATIC
        IMPORTED
)
set_target_properties(
        onnxifi_loader
        PROPERTIES IMPORTED_LOCATION
        ${CMAKE_CURRENT_LIST_DIR}/src/main/jniLibs/${ANDROID_ABI}/libonnxifi_loader.a
)

add_library(
        cpuinfo
        STATIC
        IMPORTED
)
set_target_properties(
        cpuinfo
        PROPERTIES IMPORTED_LOCATION
        ${CMAKE_CURRENT_LIST_DIR}/src/main/jniLibs/${ANDROID_ABI}/libcpuinfo.a
)

add_library(
    NNPACK
    STATIC
    IMPORTED
    )
set_target_properties(
    NNPACK
    PROPERTIES IMPORTED_LOCATION
    ${CMAKE_CURRENT_LIST_DIR}/src/main/jniLibs/${ANDROID_ABI}/libnnpack.a
    )

add_library(
        QNNPACK
        STATIC
        IMPORTED
)
set_target_properties(
        QNNPACK
        PROPERTIES IMPORTED_LOCATION
        ${CMAKE_CURRENT_LIST_DIR}/src/main/jniLibs/${ANDROID_ABI}/libqnnpack.a
)


include_directories( src/main/cpp )

find_library(
     log-lib
     log
     )

target_link_libraries(
        native-lib
        -Wl,--whole-archive
        caffe2
        -Wl,--no-whole-archive
        NNPACK
        QNNPACK
        caffe2_protos
#        caffe2_detectron_ops
        onnx_proto
        onnx
        onnxifi_loader
        c10
        protobuf
        cpufeatures
        thread_pool
        cpuinfo
        clog

        ${log-lib}
        ${android-lib})