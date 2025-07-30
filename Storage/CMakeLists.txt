set(TGT Storage)

set(SRC_LIST
    "FilesystemUtil.cc"
    "Layout.cc"
    "Log.cc"
    "LogFactory.cc"
    "MemoryLog.cc"
    "SegmentedLog.cc"
    "SimpleFileLog.cc"
    "SnapshotFile.cc"
    "SegmentedLog.proto"
    "SimpleFileLog.proto"
)

add_library(${TGT} STATIC
    ${SRC_LIST}
)

protobuf_generate(
    TARGET ${TGT}
    IMPORT_DIRS ${PROJECT_SOURCE_DIR}
)

target_include_directories(${TGT}
    PUBLIC ${PROJECT_SOURCE_DIR}
    ${CMAKE_CURRENT_BINARY_DIR}
)

target_link_libraries(${TGT}
    PUBLIC
    protobuf::libprotoc
    protobuf::libprotobuf
    protobuf::libprotobuf-lite
    Protocol
)