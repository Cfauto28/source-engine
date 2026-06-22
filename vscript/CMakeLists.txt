project(vscript)
add_library(vphysics SHARED
		vscript.cpp
		vscript_squirrel.cpp
		vscript_bindings_base.cpp
		vscript_bindings_math.cpp
		./squirrel/sqstdlib/sqstdaux.cpp
		./squirrel/sqstdlib/sqstdblob.cpp
		./squirrel/sqstdlib/sqstdio.cpp
		./squirrel/sqstdlib/sqstdmath.cpp
		./squirrel/sqstdlib/sqstdrex.cpp
		./squirrel/sqstdlib/sqstdstream.cpp
		./squirrel/sqstdlib/sqstdstring.cpp
		./squirrel/sqstdlib/sqstdsystem.cpp
		./squirrel/squirrel/sqapi.cpp
		./squirrel/squirrel/sqbaselib.cpp
		./squirrel/squirrel/sqclass.cpp
		./squirrel/squirrel/sqcompiler.cpp
		./squirrel/squirrel/sqdebug.cpp
		./squirrel/squirrel/sqfuncstate.cpp
		./squirrel/squirrel/sqlexer.cpp
		./squirrel/squirrel/sqmem.cpp
		./squirrel/squirrel/sqobject.cpp
		./squirrel/squirrel/sqstate.cpp
		./squirrel/squirrel/sqtable.cpp
		./squirrel/squirrel/sqvm.cpp
)

target_include_directories(vscript PUBLIC ./squirrel/include ../public/tier0 ../public/tier1)
target_compile_definitions(vscript PUBLIC MAPBASE_VSCRIPT)

add_dependencies(tier0 tier1 )
target_link_libraries(vscript PUBLIC tier0 tier1)

install(TARGETS vscript DESTINATION bin)
