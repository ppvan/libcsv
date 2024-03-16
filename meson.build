project('libcsv', 'c',
  version : '3.0.3',
  default_options : ['warning_level=3'])

inc = include_directories('.')
install_headers('csv.h')

sources = ['libcsv.c']

libcsv = shared_library('csv',
    sources,
    include_directories: inc,
    install: true
)


executable('testcsv', 'test_csv.c', include_directories: inc, link_with: [libcsv])


pkg_mod = import('pkgconfig')
pkg_mod.generate(libraries : libcsv,
                 version : '3.0.3',
                 name : 'libcsv',
                 filebase : 'csv',
                 description : 'Fast CSV parser')