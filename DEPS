vars = {
  'git_url': 'https://chromium.googlesource.com',
}

deps = {
  'src/buildtools':
       Var('git_url') + '/chromium/buildtools.git@39b1db2ab4aa4b2ccaa263c29bdf63e7c1ee28aa',
  'src/build':
       Var('git_url') + '/chromium/src/build.git@7321edc3e835447b4ec75732ab683fb70ad1a5fd',
  'src/build_overrides':
       Var('git_url') + '/chromium/src/build_overrides.git@4e8813862084fbe60077ed71b492bf1a6afeffcf',
  'src/tools/gyp':
       Var('git_url') + '/external/gyp.git@e7079f0e0e14108ab0dba58728ff219637458563',
}

hooks = [
  {
    'action': [
      'download_from_google_storage',
      '--no_resume',
      '--platform=win32',
      '--no_auth',
      '--bucket',
      'chromium-gn',
      '-s',
      'src/buildtools/win/gn.exe.sha1'
    ],
    'pattern':
      '.',
    'name':
      'gn_win'
  },
  {
    'action': [
      'download_from_google_storage',
      '--no_resume',
      '--platform=darwin',
      '--no_auth',
      '--bucket',
      'chromium-gn',
      '-s',
      'src/buildtools/mac/gn.sha1'
    ],
    'pattern':
      '.',
    'name':
      'gn_mac'
  },
  {
    'action': [
      'download_from_google_storage',
      '--no_resume',
      '--platform=linux*',
      '--no_auth',
      '--bucket',
      'chromium-gn',
      '-s',
      'src/buildtools/linux64/gn.sha1'
    ],
    'pattern':
      '.',
    'name':
      'gn_linux64'
  },
  {
    'action': [
      'download_from_google_storage',
      '--no_resume',
      '--platform=win32',
      '--no_auth',
      '--bucket',
      'chromium-clang-format',
      '-s',
      'src/buildtools/win/clang-format.exe.sha1'
    ],
    'pattern':
      '.',
    'name':
      'clang_format_win'
  },
  {
    'action': [
      'download_from_google_storage',
      '--no_resume',
      '--platform=darwin',
      '--no_auth',
      '--bucket',
      'chromium-clang-format',
      '-s',
      'src/buildtools/mac/clang-format.sha1'
    ],
    'pattern':
      '.',
    'name':
      'clang_format_mac'
  },
  {
    'action': [
      'download_from_google_storage',
      '--no_resume',
      '--platform=linux*',
      '--no_auth',
      '--bucket',
      'chromium-clang-format',
      '-s',
      'src/buildtools/linux64/clang-format.sha1'
    ],
    'pattern':
      '.',
    'name':
      'clang_format_linux'
  },
  {
    'action': [
      'python',
      'src/build/linux/sysroot_scripts/install-sysroot.py',
      '--running-as-hook'
    ],
    'pattern':
      '.',
    'name':
      'sysroot'
  },
]
