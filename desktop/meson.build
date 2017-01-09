#
# Build and install geary.desktop
#
if 'INTLTOOL_MERGE_FOUND'
  # INTLTOOL_MERGE_APPDATA(['geary.appdata.xml', 'po'])
  # INTLTOOL_MERGE_DESKTOP(['geary.desktop', 'po'])
  # INTLTOOL_MERGE_AUTOSTART_DESKTOP(['geary-autostart.desktop', 'po'])
  if 'DESKTOP_VALIDATE'
    if 'DESKTOP_FILE_VALIDATE_FOUND'
      # VALIDATE_DESKTOP_FILE('geary.desktop')
      # VALIDATE_DESKTOP_FILE('geary-autostart.desktop')
    else
      # message(['FATAL_ERROR', 'desktop-file-validate must be installed to validate generated .desktop file'])
    endif
  endif
else
  # message(['FATAL_ERROR', 'intltool must be installed to generate .desktop file'])
endif
# Optional: run update-desktop-database at install time.
# (This has to happen after the geary.desktop file is installed.)
if 'DESKTOP_UPDATE'
  # install(['CODE', 'execute_process (COMMAND update-desktop-database)', 'CODE', 'message (STATUS \"Updating desktop database\")'])
  # add_custom_target(['uninstall-desktop-update', 'COMMAND', 'update-desktop-database'])
  # add_dependencies(['post-uninstall', 'uninstall-desktop-update'])
else
  # install(['CODE', 'message (STATUS \"Not updating desktop database\")'])
endif
if 'DISABLE_CONTRACT'
  # message(['STATUS', 'Install Contractor contract: OFF'])
else
  # message(['STATUS', 'Install Contractor contract: ON'])
  if 'INTLTOOL_MERGE_FOUND'
    # INTLTOOL_MERGE_CONTRACT(['geary-attach.contract', 'po'])
    # Can't validate Contractor file since it isn't a valid Desktop
    # file according to desktop-file-validate from desktop-file-utils 0.22:
    # - geary-attach.contract: error: first group is not "Desktop Entry"
    # - geary-attach.contract: error: file contains group "Contractor Entry",
    #       but groups extending the format should start with "X-"
    # - geary-attach.contract: error: filename does not have a .desktop extension
    #
    #        if (DESKTOP_VALIDATE)
    #            if (DESKTOP_FILE_VALIDATE_FOUND)
    #                VALIDATE_DESKTOP_FILE (geary-attach.contract)
    #            endif (DESKTOP_FILE_VALIDATE_FOUND)
    #        endif (DESKTOP_VALIDATE)
  endif
  # install(['PROGRAMS', 'geary-attach', 'DESTINATION', 'bin'])
endif
