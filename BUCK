load('//:subdir_glob.bzl', 'subdir_glob')

cxx_library(
  name = 'benchmark',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('include', '**/*.hpp'),
    ('include', '**/*.h'),
  ]),
  headers = subdir_glob([
    ('src', '**/*.h'),
  ]),
  srcs = glob([
    'src/**/*.cc',
  ], exclude = [
    'src/benchmark_main.cc',
  ]),
  licenses = [
    'LICENSE',
  ],
  exported_linker_flags = [
    '-pthread',
  ],
  visibility = [
    'PUBLIC',
  ],
)

cxx_binary(
  name = 'benchmark_main',
  srcs = [
    'src/benchmark_main.cc',
  ],
  deps = [
    ':benchmark',
  ],
)
