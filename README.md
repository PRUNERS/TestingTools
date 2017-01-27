<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#org98f9835">1. Description</a></li>
<li><a href="#org3d7b546">2. Prerequisites</a></li>
<li><a href="#orge6a0a1a">3. Installation</a></li>
</ul>
</div>
</div>


<a id="org98f9835"></a>

# Description

This repository allow to separately build "FileCheck" and "llvm-lit"
from LLVM. It has *[llvm-mirror/llvm/](https://github.com/llvm-mirror/llvm.git) as sub-module and a custom
/CMakeLists.txt* to separately build and install those two tools.


<a id="org3d7b546"></a>

# Prerequisites

To compile the TestingTools you need an host Clang/LLVM version >= 3.9, a
CMake version >= 3.4.3.

Ninja build system is preferred. For more information how to obtain
Ninja visit <https://martine.github.io/ninja>.


<a id="orge6a0a1a"></a>

# Installation

    git clone git@github.com:PRUNERS/TestingTools.git
    cd TestingTools
    mkdir build && cd build
    cmake -G Ninja \
     -D CMAKE_CXX_COMPILER=clang++ \
     -D CMAKE_INSTALL_PREFIX:PATH=/install/path \
     -DCMAKE_CXX_FLAGS="-fno-rtti" \
     ..
    ninja && ninja install
