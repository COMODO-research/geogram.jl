# Geogram.jl

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://github.com/COMODO-research/Geogram.jl/blob/main/LICENSE)

## Description 
This project is a Julia wrapper for the [geogram C++ project](https://github.com/BrunoLevy/geogram). 

For the moment the only functionality exposed by this wrapper is the remeshing (`vorpalite`) functionality in Geogram, which enables smooth remeshing of surfaces. Secondly the wrapper currently works by exporting a .obj file, calling Geogram as an external executable using `run` with desired parameters set, and importing of the output .obj file. In the future the wrapper should feature a more complete and efficient interface by directly interfacing with the C++ code through Julia (e.g. using `ccall`). 

![](assets/img/ggremesh_example_01.png)  

# Installation
```julia
julia> ]
(@v1.xx) pkg> add https://github.com/COMODO-research/Geogram.jl
```

or 

```julia
julia> using Pkg
julia> Pkg.add(url = "https://github.com/COMODO-research/Geogram.jl")
```

# Getting started
To get started install the package, study the documentation, and test some of the demos provided in the [`examples`](https://github.com/COMODO-research/Geogram.jl/tree/main/examples) folder. 

# Documentation 
Under construction, see the demos provided for assistance at the moment. 

# External dependancies
This project is a wrapper for Geogram. Currently the project ships with executables for `vorpalite` (which is part of geogram) for [Linux, Windows, and Mac](https://github.com/COMODO-research/Geogram.jl/tree/main/ext/geogram). Depending on your operating system, you may want to or need to compile the source yourself, here are some basic instructions for Linux: 

```
git clone --recurse-submodules https://github.com/BrunoLevy/geogram.git
cd geogram
./configure.sh
cd build/Linux64-gcc-dynamic-Release
make -j 8
cp bin/vorpalite <path to Geomgram.jl>/lib_ext/geogram/lin64/bin/vorpalite
```
In future releases the above should not be needed as the source code will be called by Julia directly. 

# Testing 
Under constructionm, basic manual testing is available through the demos in the examples folder. 

# Roadmap
- [x] Provide basic file export/import wrapping functionality (no `ccall` interface)
- [ ] Create proper `ccall`-based interface 

# How to contribute? 
Your help would be greatly appreciated! If you can contribute please do so by posting a pull-request. I am very much open to fully acknowledging your contributions e.g. by listing you as a contributor properly whereever possible, by welcoming you on board as a long term contributor, or by inviting you to be a co-author on publications featuring Geogram.jl functionality. 

# License 
Geogram.jl is released open source under the [MIT license](https://github.com/COMODO-research/Geogram.jl/blob/main/LICENSE).

# References and links for Geogram

* Geogram GitHub repository: https://github.com/BrunoLevy/geogram
* [Lévy B., Bonneel N. (2013) Variational Anisotropic Surface Meshing with
Voronoi Parallel Linear Enumeration. In: Jiao X., Weill JC. (eds)
Proceedings of the 21st International Meshing Roundtable. Springer,
Berlin, Heidelberg. doi: 10.1007/978-3-642-33573-0_21](https://doi.org/10.1007/978-3-642-33573-0_21 ) 
* https://inria.hal.science/hal-00804558/file/vorpaline.pdf
* https://www.ljll.math.upmc.fr/hecht/ftp/ff++days/2013/BrunoLevy.pdf

