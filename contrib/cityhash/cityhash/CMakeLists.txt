ADD_LIBRARY (cityhash STATIC
    city.cc
)

set_property(TARGET cityhash PROPERTY POSITION_INDEPENDENT_CODE ON)

ADD_LIBRARY (cityhash::cityhash ALIAS cityhash)

IF (NOT BUILD_SHARED_LIBS)
    IF (NOT WITH_SYSTEM_CITYHASH)
        INSTALL (TARGETS cityhash
            ARCHIVE DESTINATION lib
            LIBRARY DESTINATION lib
        )
    ENDIF()
ENDIF()
