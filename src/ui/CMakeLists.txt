# ASEPRITE
# Copyright (C) 2001-2016  David Capello


# Debug C/C++ flags
if(CMAKE_BUILD_TYPE STREQUAL Debug)
  if(LINUX)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Og")
    set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Og")
  endif()
else()
  if (LINUX OR APPLE)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O2")
    set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -O2")
  endif()
endif()

if(WIN32)
  add_definitions(-D_CRT_SECURE_NO_WARNINGS)
endif()

add_library(ui-lib
  accelerator.cpp
  alert.cpp
  box.cpp
  button.cpp
  combobox.cpp
  cursor.cpp
  custom_label.cpp
  entry.cpp
  graphics.cpp
  grid.cpp
  image_view.cpp
  int_entry.cpp
  intern.cpp
  label.cpp
  link_label.cpp
  listbox.cpp
  listitem.cpp
  manager.cpp
  menu.cpp
  message.cpp
  message_loop.cpp
  move_region.cpp
  overlay.cpp
  overlay_manager.cpp
  paint_event.cpp
  panel.cpp
  popup_window.cpp
  property.cpp
  register_message.cpp
  resize_event.cpp
  scroll_bar.cpp
  scroll_helper.cpp
  separator.cpp
  size_hint_event.cpp
  slider.cpp
  splitter.cpp
  system.cpp
  textbox.cpp
  theme.cpp
  timer.cpp
  tooltips.cpp
  view.cpp
  viewport.cpp
  widget.cpp
  window.cpp)

target_link_libraries(ui-lib
  she
  clip
  gfx-lib
  base-lib
  ${PIXMAN_LIBRARY})
