cmake_minimum_required (VERSION 2.6)
project (htslib)

include_directories ("${PROJECT_SOURCE_DIR}/htslib")
add_subdirectory (htslib)

add_executable (htscmd main.c samview.c vcfview.c bamidx.c bcfidx.c bamshuf.c bam2fq.c tabix.c abreak.c bam2bed.c vcfcheck.c vcfisec.c vcfmerge.c)
target_link_libraries (htscmd hts z m pthread)

#install (TARGETS libhts DESTINATION bin)
#install (FILES hts.h DESTINATION include)

install (TARGETS htscmd DESTINATION bin)
