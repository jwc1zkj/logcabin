set(TGT Client)

set(SRC_LIST
    "Backoff.cc",
    "Client.cc",
    "ClientImpl.cc",
    "LeaderRPC.cc",
    "MockClientImpl.cc",
    "SessionManager.cc",
    "Util.cc",
)

add_library(${TGT} STATIC
    ${SRC_LIST}
)


set(TGT ServerControl)

add_executable(${TGT}
    "ServerControl.cc"
)

target_link_libraries(${TGT} PRIVATE
    "liblogcabin"
    "pthread",
    "protobuf",
    "rt",
    "cryptopp"
)