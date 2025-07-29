set(TGT Event)

add_library(${TGT} STATIC
    "File.cc"
    "Loop.cc"
    "Signal.cc"
    "Timer.cc"
)

target_include_directories(${TGT}
    PUBLIC ${PROJECT_SOURCE_DIR}
)
