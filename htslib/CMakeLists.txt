set (HTS_SOURCES knetfile.c bgzf.c hts.c vcf.c sam.c tbx.c synced_bcf_reader.c vcfutils.c)
set (BGZF_DEFINES "-D_USE_KNETFILE -DBGZF_MT -DBGZF_CACHE")

add_library (hts SHARED ${HTS_SOURCES})
add_library (hts-static STATIC ${HTS_SOURCES})
set_source_files_properties (bgzf.c PROPERTIES COMPILE_FLAGS ${BGZF_DEFINES})

set_target_properties (hts-static PROPERTIES OUTPUT_NAME "hts")
set_target_properties (hts-static PROPERTIES PREFIX "lib")

SET_TARGET_PROPERTIES(hts PROPERTIES CLEAN_DIRECT_OUTPUT 1)
SET_TARGET_PROPERTIES(hts-static PROPERTIES CLEAN_DIRECT_OUTPUT 1)
