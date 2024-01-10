function (bin_test_simple)
    set (name "test_cpp_simple")
    
    set (src 
        "${CMAKE_CURRENT_SOURCE_DIR}/main.cpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/stub.cpp")

    set (link
        ${STARTUP_LIB_NAME})

    add_executable(${name} ${src})

    set_source_files_properties(
        "${CMAKE_CURRENT_SOURCE_DIR}/stub.cpp"
        PROPERTIES COMPILE_FLAGS ${CC_FLAGS} -fno-builtin-exit
        )
    
    target_link_libraries (${name} ${link})
    link_app (${name})
endfunction ()

#################################################################

bin_test_simple()
