# csCatch2
a wrapper over eigen library to easy manage with cmake presets

## How to Build

- checkout in a folder, e.g., `projects/csEigen` where `csCMake` has already been checked out in `projects/csCMake`
  - your folder structure will look like
```
projects
  csCMake
    csCMake.cmake
    ...
  csEigen
    csEigen
      README.md
      ...
```  
- get `eigen-3.4.0` (e.g. as zip) and extract in `eigen-3.4.0` folder
- create a `cmakeUserPath.json` file with  your settings for path. The following should be sufficient
```
{
  "version":  10,
  "configurePresets": [
    {
      "name": "cmake-user-path-msvc2022-x64",
      "hidden": true
    },
    {
      "name": "cmake-user-path-msvc2022-x64-LLVM",
      "hidden": true
    }
  ]
}
```
- check now your folder contains
```
projects
  csCMake
    csCMake.cmake
    ...
  csEigen
    csEigen
      eigen-3.4.0
      README.md
      cmakeUserPath.json
      ...
```  

- compile with one of the available workflows, e.g.,
```
cmake --workflow msvc2022-x64
```

## Available workflows

- `msvc2022-x64`
- `msvc2022-x64-LLVM`

## TODO list
- add automatic checkout/download of `eigen-3.4.0` folder via cmake