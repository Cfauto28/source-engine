project(togl)
add_library(togl SHARED
		linuxwin/dx9asmtogl2.cpp
		linuxwin/dxabstract.cpp
		linuxwin/glentrypoints.cpp
		linuxwin/glmgr.cpp
		linuxwin/glmgrbasics.cpp'
		linuxwin/cglmtex.cpp
		linuxwin/cglmfbo.cpp
		linuxwin/cglmprogram.cpp
		linuxwin/cglmbuffer.cpp
		linuxwin/cglmquery.cpp
		linuxwin/asanstubs.cpp
)

target_compile_definitions(togl PUBLIC TOGL_DLL_EXPORT=1 strncpy=use_Q_strncpy_instead _snprintf=use_Q_snprintf_instead)
target_include_directories(togl PUBLIC ./ ../public ../public/tier0 ../public/tier1 ../thirdparty/SDL)

add_dependencies(togl tier0 tier1 tier2 vstdlib mathlib)
target_link_libraries(togl PUBLIC tier0 tier1 tier2 vstdlib mathlib)

if(APPLE)
    target_sources(togl PUBLIC linuxwin/glmgrcocoa.mm)
    target_link_libraries(togl PUBLIC opengl carbon)
endif()

install(TARGETS togl DESTINATION bin)
