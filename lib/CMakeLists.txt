LIST_FILES(lib.sources LIB_SOURCES "*.cpp")
ADD_PCH_RULE(static.h LIB_SOURCES)
ADD_LIBRARY(${PROJECT_LIB} STATIC ${LIB_SOURCES})
SET_TARGET_PROPERTIES(${PROJECT_LIB} PROPERTIES OUTPUT_NAME ${PROJECT_NAME})
ADD_DEPENDENCIES(${PROJECT_LIB} lib.sources)
SET_TARGET_PROPERTIES( ${PROJECT_LIB}
  PROPERTIES COMPILE_FLAGS "-Winvalid-pch -include ${PROJECT_PCH}")

