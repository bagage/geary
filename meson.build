project('geary', 'vala', 'c')

if meson.get_compiler('c').get_id() == 'clang'
    add_global_arguments('-fdiagnostics-color', language: 'c')
endif

gnome = import('gnome')
i18n = import('i18n')

subdir('ui')
subdir('po')
subdir('src')

install_subdir('sql', install_dir: 'share/geary/sql')