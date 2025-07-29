set(TGT Tree)

find_package(Protobuf REQUIRED)

set(SRC_LIST
    "ProtoBuf.cc"
    "Tree.cc"
    "Snapshot.proto"
)

add_library(${TGT} STATIC
    ${SRC_LIST}
)

protobuf_generate(
    TARGET ${TGT}
)

target_include_directories(${TGT}
    PUBLIC ${PROJECT_SOURCE_DIR}
)

target_link_libraries(${TGT}
    PUBLIC
    protobuf::libprotoc
    protobuf::libprotobuf
    protobuf::libprotobuf-lite
    Protocol
)