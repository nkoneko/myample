Build
---------

```
$ git clone --recursive https://github.com/nkoneko/myample meow
$ cd meow
$ mkdir build
$ cd build
$ cmake .. -DBUILD_SHARED_LIBS=ON
$ make -j8
```

Run
---------

```
$ cd build
$ cling -std=c++14 -I../re2
****************** CLING ******************
* Type C++ code and press enter to run it *
*             Type .q to exit             *
*******************************************
[cling]$ .L re2/libre2.dylib
[cling]$ #include <re2/re2.h>
[cling]$ RE2 pattern("ab[cde]");
[cling]$ RE2::PartialMatch("aabbabee", pattern)
(bool) true
[cling]$ RE2::PartialMatch("aabbababcdd", pattern)
(bool) true
[cling]$ RE2::PartialMatch("abffafbf", pattern)
(bool) false
[cling]$
```
