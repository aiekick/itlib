itlib: iboB's Template Library
==============================

A collection of small single-header C++ libraries similar to the C++ standard library. See below for a list.

[![Language](https://img.shields.io/badge/language-C++-blue.svg)](https://isocpp.org/) [![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)

itlib library used to be [chobo-shl](https://github.com/Chobolabs/chobo-shl) which is no longer supported. New libraries and updates to the existing ones will be added here.

## Build Status

*TODO: add github actions*

## Libraries

Every `.hpp` file in `include/itlib` is a standalone library and has no dependencies other than the standard lib.

Documentation is provided in comments at the top of each file.

**[flat_map.hpp](https://github.com/iboB/itlib/blob/master/include/itlib/flat_map.hpp)** [![Standard](https://img.shields.io/badge/C%2B%2B-11-blue.svg)](https://en.wikipedia.org/wiki/C%2B%2B#Standardization)

> A class with the interface of `std::map` but implemented with an underlying `std::vector`-type container, thus providing better cache locality of the elements. Similar to [`boost::flat_map`](http://www.boost.org/doc/libs/1_61_0/doc/html/boost/container/flat_map.html) with the notable difference that the underlying container can be changed via a template argument (thus making the class not strictly an `std::map` drop-in replacement)

**[memory_view.hpp](https://github.com/iboB/itlib/tree/master/include/itlib/memory_view.hpp)** [![Standard](https://img.shields.io/badge/C%2B%2B-11-blue.svg)](https://en.wikipedia.org/wiki/C%2B%2B#Standardization)

> A class which provides a std::vector like interface (sans the methods which might change the size or capacity) to a chunk of memory. Similar to C++20's `span`

**[small_vector.hpp](https://github.com/iboB/itlib/tree/master/include/itlib/small_vector.hpp)** [![Standard](https://img.shields.io/badge/C%2B%2B-11-blue.svg)](https://en.wikipedia.org/wiki/C%2B%2B#Standardization)

> A mix between a `vector` and a `static_vector`. It's a dynamic array, optimized for use when the number of elements is small. Like `static_vector` is has a static buffer with a given capacity, but can fall back to dynamically allocated memory, should the size exceed it. Similar to [`boost::small_vector`](http://www.boost.org/doc/libs/1_61_0/doc/html/boost/container/small_vector.html)

**[static_vector.hpp](https://github.com/iboB/itlib/tree/master/include/itlib/static_vector.hpp)** [![Standard](https://img.shields.io/badge/C%2B%2B-11-blue.svg)](https://en.wikipedia.org/wiki/C%2B%2B#Standardization)

> A mix between `std::vector` and `std::array`: A dynamically sized container with fixed capacity (supplied as a template parameter). This allows you to have dynamically sized vectors on the stack or as cache-local value members, as long as you know a big enough capacity beforehand. Similar to [`boost::static_vector`](http://www.boost.org/doc/libs/1_61_0/doc/html/boost/container/static_vector.html).

## Usage

Clone the repo or choose one or more libraries that you like and copy somewhere in your include paths.

Every library is self-contained, so you can copy, move, and modify whichever you like and not wory about interdependencies.

## Contributing

Pull requests and issues are welcome.

Please make one pull request and issue per library, tagging them with the library name in the title with brackets. Example:

* *[small_vector] Added insert methods*
* *[flat_map] Crash when using with xxxx container*

You can use CMake to generate a project and run the tests locally.

## Copyright

Copyright &copy; 2016-2019 [Chobolabs Inc.](http://www.chobolabs.com/)
Copyright &copy; 2020 Borislav Stanimirov

These libraries are distributed under the MIT Software License. See LICENSE.txt for further details or copy [here](http://opensource.org/licenses/MIT).
