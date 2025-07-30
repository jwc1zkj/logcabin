set(TGT Server)

set(SRC_LIST
    "ClientService.cc"
    "ControlService.cc"
    "Globals.cc"
    "RaftConsensus.cc"
    "RaftConsensusInvariants.cc"
    "RaftService.cc"
    "ServerStats.cc"
    "StateMachine.cc"
    "SnapshotMetadata.proto"
    "SnapshotStateMachine.proto"
    "SnapshotStats.proto"
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
    ${PROJECT_BINARY_DIR}
)

target_link_libraries(${TGT}
    PUBLIC
    protobuf::libprotoc
    protobuf::libprotobuf
    protobuf::libprotobuf-lite
    Protocol
)