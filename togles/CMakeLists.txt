project(togles)
add_library(togles SHARED
        linuxwin/dx9asmtogl2.cpp
        linuxwin/dxabstract.cpp
        linuxwin/glentrypoints.cpp
        linuxwin/glmgr.cpp
        linuxwin/glmgrbasics.cpp
        linuxwin/cglmtex.cpp
        linuxwin/cglmfbo.cpp
        linuxwin/cglmprogram.cpp
        linuxwin/cglmbuffer.cpp
        linuxwin/cglmquery.cpp
        linuxwin/asanstubs.cpp
        linuxwin/decompress.c
)

target_compile_definitions(togles PUBLIC TOGL_DLL_EXPORT=1 strncpy=use_Q_strncpy_instead _snprintf=use_Q_snprintf_instead)
target_include_directories(togles PUBLIC ./ ../public ../public/tier0 ../public/tier1 ../thirdparty/SDL)

add_dependencies(togles tier0 tier1 tier2 vstdlib mathlib)
target_link_libraries(togles PUBLIC tier0 tier1 tier2 vstdlib mathlib)

if(APPLE)
    target_sources(togles PUBLIC linuxwin/glmgrcocoa.mm)
    target_link_libraries(togles PUBLIC opengl carbon)
endif()

install(TARGETS togles DESTINATION bin)
