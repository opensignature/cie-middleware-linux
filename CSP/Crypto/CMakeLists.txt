target_sources(ciepki
	PRIVATE
		"${CMAKE_CURRENT_LIST_DIR}/AES.cpp"
		"${CMAKE_CURRENT_LIST_DIR}/AES.h"
		"${CMAKE_CURRENT_LIST_DIR}/ASNParser.cpp"
		"${CMAKE_CURRENT_LIST_DIR}/ASNParser.h"
		"${CMAKE_CURRENT_LIST_DIR}/Base64.cpp"
		"${CMAKE_CURRENT_LIST_DIR}/Base64.h"
		"${CMAKE_CURRENT_LIST_DIR}/DES3.cpp"
		"${CMAKE_CURRENT_LIST_DIR}/DES3.h"
		"${CMAKE_CURRENT_LIST_DIR}/MAC.cpp"
		"${CMAKE_CURRENT_LIST_DIR}/MAC.h"
		"${CMAKE_CURRENT_LIST_DIR}/MD5.cpp"
		"${CMAKE_CURRENT_LIST_DIR}/MD5.h"
		"${CMAKE_CURRENT_LIST_DIR}/RSA.cpp"
		"${CMAKE_CURRENT_LIST_DIR}/RSA.h"
		"${CMAKE_CURRENT_LIST_DIR}/SHA1.cpp"
		"${CMAKE_CURRENT_LIST_DIR}/SHA1.h"
		"${CMAKE_CURRENT_LIST_DIR}/SHA256.cpp"
		"${CMAKE_CURRENT_LIST_DIR}/sha256.h"
		"${CMAKE_CURRENT_LIST_DIR}/SHA512.cpp"
		"${CMAKE_CURRENT_LIST_DIR}/sha512.h"
	PUBLIC
		#"${CMAKE_CURRENT_LIST_DIR}/foo.h"
	)


find_path(PCSCLITE_INCLUDE pcsclite.h WinSCard.h
	        HINTS ${PC_PCSC_INCLUDEDIR} ${PC_PCSC_INCLUDE_DIRS}
		        PATH_SUFFIXES PCSC)
#find_library(MY_LIB mylib)
#target_link_libraries(ciepki PUBLIC ${PCSCLITE_LIBRARY})
#target_compile_definitions(ciepki PUBLIC USE_MY)
target_include_directories(ciepki PRIVATE "${CMAKE_CURRENT_LIST_DIR}" "${PCSCLITE_INCLUDE}")
