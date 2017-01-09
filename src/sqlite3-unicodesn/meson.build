sqlite3_unicodesn_src = [
    'fts3_unicode2.c',
    'fts3_unicodesn.c',
    'static.c',
    'libstemmer_c/runtime/api_sq3.c',
    'libstemmer_c/runtime/utilities_sq3.c'
]

sqlite3_defines = [
    '-D', 'SQLITE_ENABLE_FTS4', 
    '-D', 'SQLITE_ENABLE_FTS4_UNICODE61',
    '-D', 'HAVE_FTS3_TOKENIZER',
]

sqlite3_unicodesn_stemmers = ['danish', 'dutch', 'english', 'finnish', 'french', 'german', 'hungarian', 'italian', 'norwegian', 'portuguese', 'romanian', 'russian', 'spanish', 'swedish', 'turkish']
foreach stemmer : sqlite3_unicodesn_stemmers
    sqlite3_unicodesn_src += 'libstemmer_c/src_c/stem_UTF_8_' + stemmer + '.c'
    sqlite3_defines += ['-D', 'WITH_STEMMER_' + stemmer]
endforeach

sqlite3_unicodesn_incdirs = include_directories(['libstemmer_c/runtime', 'libstemmer_c/src_c'])
sqlite3_dep = dependency('sqlite3', version: '>=3.7.4')
sqlite3_unicodesn_lib = static_library('sqlite3-unicodesn', 
                                        sqlite3_unicodesn_src, 
                                        c_args: sqlite3_defines,
                                        include_directories: sqlite3_unicodesn_incdirs,
                                        dependencies: sqlite3_dep)
