cmake_minimum_required(VERSION 2.4)

project(IdentifierRandomizer)

option(withParaView "Enable ParaView support" true)
set(withParaView true)

# path to the common code base
find_path(TTK_DIR ttk.cmake
  PATHS
    core/
    ../core/
    ../../core/
    ../../../core/
    sandbox/core/
    sandbox/../core/
    sandbox/../../core/
    sandbox/../../../core/
)
include(${TTK_DIR}/ttk.cmake)

# include the vtk wrapper for your TTK package 
ttk_add_vtkWrapper_package(vtkIdentifierRandomizer)

# Add the plugin
ttk_wrapup_paraview_plugin(
  IdentifierRandomizer
  1.0)
