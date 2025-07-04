# add_executable(backpack-B
#         backpack-B.cpp
# )
# target_link_libraries(backpack-B PUBLIC
#         rby1-sdk::rby1-sdk
#         DynamixelSDK
# )
# target_compile_definitions(backpack-B PUBLIC -DMODEL_PATH="${MODEL_PATH}")


# 예제 목록 정의
set(EXAMPLES
    backpack-B
    stand-B
    stand-P
)

# 각 예제마다 실행 파일 생성
foreach(SRC IN LISTS EXAMPLES)
    set(EXECUTABLE_NAME ${SRC})
    add_executable(${EXECUTABLE_NAME}
        ${SRC}.cpp
    )
    target_link_libraries(${EXECUTABLE_NAME} PRIVATE
        rby1-sdk::rby1-sdk
        DynamixelSDK
    )
    target_compile_definitions(${EXECUTABLE_NAME} PUBLIC
        -DMODEL_PATH="${MODEL_PATH}"
    )
    message(STATUS "Added executable: ${EXECUTABLE_NAME}")
endforeach()