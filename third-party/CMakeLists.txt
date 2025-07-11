set(DynamixelSDK_SRC_PATH ${CMAKE_CURRENT_SOURCE_DIR}/DynamixelSDK/c++/src/dynamixel_sdk)
set(DynamixelSDK_SRCS
        ${DynamixelSDK_SRC_PATH}/group_bulk_read.cpp
        ${DynamixelSDK_SRC_PATH}/group_bulk_write.cpp
        ${DynamixelSDK_SRC_PATH}/group_fast_bulk_read.cpp
        ${DynamixelSDK_SRC_PATH}/group_fast_sync_read.cpp
        ${DynamixelSDK_SRC_PATH}/group_handler.cpp
        ${DynamixelSDK_SRC_PATH}/group_sync_read.cpp
        ${DynamixelSDK_SRC_PATH}/group_sync_write.cpp
        ${DynamixelSDK_SRC_PATH}/packet_handler.cpp
        ${DynamixelSDK_SRC_PATH}/port_handler.cpp
        # ${DynamixelSDK_SRC_PATH}/port_handler_linux.cpp
        ${DynamixelSDK_SRC_PATH}/protocol1_packet_handler.cpp
        ${DynamixelSDK_SRC_PATH}/protocol2_packet_handler.cpp
)
if (APPLE)
    set(DynamixelSDK_SRCS
            ${DynamixelSDK_SRCS}
            ${DynamixelSDK_SRC_PATH}/port_handler_mac.cpp
    )
elseif (WIN32)
    set(DynamixelSDK_SRCS
            ${DynamixelSDK_SRCS}
            ${DynamixelSDK_SRC_PATH}/port_handler_windows.cpp
    )
else ()
    set(DynamixelSDK_SRCS
            ${DynamixelSDK_SRCS}
            ${DynamixelSDK_SRC_PATH}/port_handler_linux.cpp
    )
endif ()
add_library(DynamixelSDK
        ${DynamixelSDK_SRCS}
)
target_include_directories(DynamixelSDK PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/DynamixelSDK/c++/include/dynamixel_sdk)