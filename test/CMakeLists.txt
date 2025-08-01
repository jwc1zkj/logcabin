set(TGT test)

find_package(GTest REQUIRED)

file(GLOB TEST_SRC_LIST RELATIVE ${CMAKE_CURRENT_SOURCE_DIR}
    "${PROJECT_SOURCE_DIR}/Core/*Test.cc"
    "${PROJECT_SOURCE_DIR}/Core/*Mock.cc"
    "${PROJECT_SOURCE_DIR}/Event/*Test.cc"
    "${PROJECT_SOURCE_DIR}/Event/*Mock.cc"
    "${PROJECT_SOURCE_DIR}/RPC/*Test.cc"
    "${PROJECT_SOURCE_DIR}/RPC/*Mock.cc"
    "${PROJECT_SOURCE_DIR}/Protocol/*Test.cc"
    "${PROJECT_SOURCE_DIR}/Protocol/*Mock.cc"
    "${PROJECT_SOURCE_DIR}/Tree/*Test.cc"
    "${PROJECT_SOURCE_DIR}/Tree/*Mock.cc"
    "${PROJECT_SOURCE_DIR}/Client/*Test.cc"
    "${PROJECT_SOURCE_DIR}/Client/*Mock.cc"
    "${PROJECT_SOURCE_DIR}/Storage/*Test.cc"
    "${PROJECT_SOURCE_DIR}/Storage/*Mock.cc"
    "${PROJECT_SOURCE_DIR}/Server/*Test.cc"
    "${PROJECT_SOURCE_DIR}/Server/*Mock.cc"
)

message(STATUS "TEST_SRC_LIST:")

foreach(f ${TEST_SRC_LIST})
    message(STATUS "    \"${f}\"")
endforeach()

add_executable(${TGT}
    "TestRunner.cc"
    ${TEST_SRC_LIST}
)

target_compile_options(${TGT}
    PRIVATE
    -fno-access-control
)

target_link_libraries(${TGT}
    PRIVATE
    Server
    Storage
    Tree
    Client
    Protocol
    RPC
    Event
    Core
    pthread
    rt
    protobuf::libprotobuf
    cryptopp::cryptopp
    GTest::gtest
    GTest::gmock
)
