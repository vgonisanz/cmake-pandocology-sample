# Pandocology sample

This is a sample how to use vgonisanz fork from cmake-pandocology

## Instructions

All md document in markdown format in doc folders. All images are in img folder. For each
project.

> If you change images or templates, maybe need to reconfigure from cmake

1. Clone this repository with cmake-pandocology:
``` git clone --recursive git@github.com:vgonisanz/cmake-pandocology-sample.git ```
1. Create build folder:
``` cd cmake-pandocology-sample/ && mkdir build && cd build ```
1. Generate makefiles:
``` cmake .. ```
1. Compile:
``` make ```

### Dependencies

* pandoc
* texlive

> Fedora complete installation (Alternatively only install texlive needed):
> sudo dnf install pandoc.x86_64 texlive-scheme-full

### Test sample doc

* Configure project with cmake
* make in build path

### Create new doc

* Copy templates/src to src folder
* Rename folder with document name
* Add/Edit CMakeLists to add new folder
* Configure project with cmake
* make in build path

## Dependencies

Use as submodule cmake-pandocology fork.
