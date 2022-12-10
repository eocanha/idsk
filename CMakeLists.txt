PROJECT(iDSK)

# See: https://stackoverflow.com/questions/10851247/how-do-i-activate-c-11-in-cmake
macro(use_cxx98)
  if (CMAKE_VERSION VERSION_LESS "3.1")
    if (CMAKE_CXX_COMPILER_ID STREQUAL "GNU")
      set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++98")
    endif ()
  else ()
    set (CMAKE_CXX_STANDARD 98)
  endif ()
endmacro(use_cxx98)

use_cxx98()

add_executable(iDSK
	src/Basic.cpp
	src/BitmapCPC.cpp
	src/Dams.cpp
	src/Desass.cpp
	src/endianPPC.cpp
	src/GestDsk.cpp
	src/getopt_pp.cpp
	src/Main.cpp
	src/Outils.cpp
	src/ViewFile.cpp
	src/Ascii.cpp
)
