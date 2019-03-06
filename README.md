# Boost CMake Nots
A collection of snippets and notes for adding minimal cmake files to boost.

## Default commit message:

```
[CMake] Add minimal cmake support

- CMake file only supports add_subdirectory workflow. 
- Provides Boost::function_types target, 
  but no installation and no unit tests.git p
```

## PR text:
```
This cmake file just provides the minimal infrastructure necessary, such that other libraries can get a sensible result from calling


    add_subdirectory( <path-to-boost_<libname>> )
    target_link_libraries( <my_lib> PUBLIC Boost::<libname> )


That assumes that all direct and indirect dependencies are also being added via `add_subdirectory` (which can e.g. happen via globbing expressions).

Some background information:

    * https://groups.google.com/forum/#!topic/boost-developers-archive/9ZdrVbAn1aU


Of course the file can be extended to e.g. build and run tests and support installation, but that is out of scope for this particular PR.

Please note that this is largely orthogonal to the recent addition to b2/boost by peter dimov, which is concerned with providing cmake config files for "classic" boost installations via b2.
```
