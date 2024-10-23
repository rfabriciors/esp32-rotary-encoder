if(IDF_VERSION_MAJOR GREATER_EQUAL 4)
    idf_component_register(SRCS "rotary_encoder.c"
        INCLUDE_DIRS include
        REQUIRES log esp_driver_gpio
    )
else()
    set(REQUIRES_COMPONENTS esp_driver_gpio)
    set(COMPONENT_ADD_INCLUDEDIRS include)
    set(COMPONENT_SRCS "rotary_encoder.c")
    register_component()
endif()