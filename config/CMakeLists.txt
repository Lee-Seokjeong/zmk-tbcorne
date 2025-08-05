if ((NOT CONFIG_ZMK_SPLIT) OR CONFIG_ZMK_SPLIT_ROLE_CENTRAL)
  zephyr_library()

  # Include the application include directory
  zephyr_include_directories(${APPLICATION_SOURCE_DIR}/include)

  zephyr_include_directories(include)
  target_sources_ifdef(CONFIG_ZMK_TRACKBALL_PIM447 config PRIVATE src/trackball_pim447.c)
  target_sources_ifdef(CONFIG_ZMK_TRACKBALL_PIM447 config PRIVATE src/trackball_pim447_led.c)

endif()
