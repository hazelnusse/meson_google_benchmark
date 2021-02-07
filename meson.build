project('MWE of meson google-benchmark transitive dependency problem', ['cpp'])

# Google benchmark library, wrap downloaded from:
# https://wrapdb.mesonbuild.com/v1/projects/google-benchmark/1.5.2/1/get_wrap
# Patch file applied is here:
# https://github.com/mesonbuild/google-benchmark/blob/1.5.2/meson.build
# subproject name must match a '.wrap' file in subprojects directory
google_benchmark_proj = subproject('google_benchmark')
google_benchmark_dep = google_benchmark_proj.get_variable('google_benchmark_dep')
google_benchmark_main_dep = google_benchmark_proj.get_variable('google_benchmark_main_dep')

# Gives linker error
mwe_main_only = executable('mwe_main_only', 'mwe.cpp', dependencies : [google_benchmark_main_dep])
test('mwe_main_only', mwe_main_only)
