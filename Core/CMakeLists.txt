set(TGT Core)

find_package(Protobuf REQUIRED)

set(SRC_LIST
    "Buffer.cc"
    "Checksum.cc"
    "ConditionVariable.cc"
    "Config.cc"
    "Debug.cc"
    "ProtoBuf.cc"
    "Random.cc"
    "RollingStat.cc"
    "ThreadId.cc"
    "Time.cc"
    "StringUtil.cc"
    "Util.cc"
    "ProtoBufTest.proto"
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