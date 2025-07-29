set(TGT RPC)

add_library(${TGT} STATIC
    "Address.cc"
    "ClientRPC.cc"
    "ClientSession.cc"
    "MessageSocket.cc"
    "OpaqueClientRPC.cc"
    "OpaqueServer.cc"
    "OpaqueServerRPC.cc"
    "Protocol.cc"
    "Server.cc"
    "ServerRPC.cc"
    "ThreadDispatchService.cc"
)

target_include_directories(${TGT}
    PUBLIC ${PROJECT_SOURCE_DIR}
)

target_link_libraries(${TGT} PRIVATE
    Core
)