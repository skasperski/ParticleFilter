cmake_minimum_required (VERSION 2.6)
project (ParticleFilter)

set(BUILD_TYPE Release)
add_definitions("-fPIC")

add_library(${PROJECT_NAME}
	map/map.c
	map/map_cspace.cpp
	map/map_draw.c
	map/map_range.c
	map/map_store.c

	pf/eig3.c
	pf/pf.c
	pf/pf_draw.c
	pf/pf_kdtree.c
	pf/pf_pdf.c
	pf/pf_vector.c)

install(FILES
	map/map.h
	pf/pf.h
	pf/pf_kdtree.h
	pf/pf_pdf.h
	pf/pf_vector.h
DESTINATION include/${PROJECT_NAME})

install(TARGETS ${PROJECT_NAME} ARCHIVE DESTINATION lib)
