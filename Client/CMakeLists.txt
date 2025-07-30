set(TGT Client)

set(SRC_LIST
    "Backoff.cc"
    "Client.cc"
    "ClientImpl.cc"
    "LeaderRPC.cc"
    "MockClientImpl.cc"
    "SessionManager.cc"
    "Util.cc"
)

add_library(${TGT} STATIC
    ${SRC_LIST}
)

target_include_directories(${TGT}
    PUBLIC ${PROJECT_SOURCE_DIR}
)

target_link_libraries(${TGT}
    PUBLIC Protocol
)
