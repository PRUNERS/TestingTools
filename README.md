<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#org8ff0d8a">1. Description</a></li>
<li><a href="#org10c7e24">2. Installation</a></li>
</ul>
</div>
</div>


<a id="org8ff0d8a"></a>

# Description

This repository allow to separately build "FileCheck" and "llvm-lit"
from LLVM. It has [llvm-mirror/llvm](https://github.com/llvm-mirror/llvm.git) as sub-module and a custom
CMakeLists.txt to separately build and install those two tools.


<a id="org10c7e24"></a>

# Installation

    git clone git@github.com:PRUNERS/TestingTools.git
    cd TestingTools
    cmake -G Ninja \
     -D CMAKE_CXX_COMPILER=clang++ \
     -D CMAKE_INSTALL_PREFIX:PATH=/install/path \
     -DCMAKE_CXX_FLAGS="-fno-rtti" \
     ..
    ninja && ninja install
