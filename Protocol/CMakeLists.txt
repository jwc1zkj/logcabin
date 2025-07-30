set(TGT Protocol)

set(SRC_LIST
    "Client.proto"
    "Raft.proto"
    "RaftLogMetadata.proto"
    "ServerControl.proto"
    "ServerStats.proto"
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
)
