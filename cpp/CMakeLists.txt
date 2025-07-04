add_executable(backpack-style
        backpack-style.cpp
)
target_link_libraries(backpack-style PUBLIC
        rby1-sdk::rby1-sdk
        DynamixelSDK
)
target_compile_definitions(backpack-style PUBLIC -DMODEL_PATH="${MODEL_PATH}")