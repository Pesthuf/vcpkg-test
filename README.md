# vcpkg-test
I can never remember the basic cmake &amp; vcpkg structure, so I made this for myself as a template. 

# Build
`cmake -B build -DCMAKE_TOOLCHAIN_FILE=*$VCPKG_ROOT/scripts/buildsystems/vcpkg.cmake`

`cmake --build build`
