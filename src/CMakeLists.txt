set(SOURCES
        AABB.h
        AABB.cpp
        FastEnvelope.cpp
        FastEnvelope.h
        #Logger.hpp
Morton.h
Morton.cpp
        Types.hpp
#common_algorithms.cpp
common_algorithms.h
)

if(FAST_ENVELOPE_WITH_GMP)
SET(SOURCES ${SOURCES} Rational.hpp)
endif()

prepend_current_path(SOURCES)
fast_envelope_copy_headers(${SOURCES})
fast_envelope_set_source_group(${SOURCES})
target_sources(FastEnvelope PRIVATE ${SOURCES})

################################################################################
# Subfolders
################################################################################

add_subdirectory(external)
