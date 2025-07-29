set(TGT Client)

find_package(cryptopp CONFIG REQUIRED)
find_package(protobuf CONFIG REQUIRED)

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

# set(TGT ServerControl)

# add_executable(${TGT}
#     "ServerControl.cc"
# )

# target_link_libraries(${TGT} PRIVATE
#     "liblogcabin"
#     "pthread"
#     "rt"
#     protobuf::libprotoc
#     protobuf::libprotobuf
#     protobuf::libprotobuf-lite
#     cryptopp::cryptopp
# )