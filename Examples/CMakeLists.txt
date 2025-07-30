set(TGT Reconfigure)

add_executable(${TGT}
    "Reconfigure.cc"
)

target_include_directories(${TGT}
    PRIVATE
    ${PROJECT_SOURCE_DIR}/include
)

target_link_libraries(${TGT}
    PRIVATE
    logcabin
)


set(TGT HelloWorld)

add_executable(${TGT}
    "HelloWorld.cc"
)

target_include_directories(${TGT}
    PRIVATE
    ${PROJECT_SOURCE_DIR}/include
)

target_link_libraries(${TGT}
    PRIVATE
    logcabin
)

set(TGT TreeOps)

add_executable(${TGT}
    "TreeOps.cc"
)

target_include_directories(${TGT}
    PRIVATE
    ${PROJECT_SOURCE_DIR}/include
)

target_link_libraries(${TGT}
    PRIVATE
    logcabin
)
