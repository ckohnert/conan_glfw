# Conanfile for the [GLFW](http://www.glfw.org/) library.

On Linux and Mac, this will download the source and compiles it.

On Windows, it will *hopefully* download the binaries provided by the dev team.

># Please submit pull requests if you can improve this package!


# Compiling/Testing instructions for this Conan package

**Note:** These instructions are only for anyone wanting to help improve *this package*.
If you're just trying to use GLFW as a dependency in your own project, simply add
`glfw/3.2@GavinNL/stable` to your requires section.

When iterating on this package itself, please follow the sequence below to
test whether the package is working for you.

In either Linux or MacOS, within the directory containing package's `conanfile.py`:

```
# Re-export the package locally
conan export GavinNL/testing
# Build it (to make sure the build commands still work)
conan install glfw/3.2@GavinNL/testing --build

# Then compile the small test project that uses it as a dependency
cd test
mkdir build
cd build
conan install .. && cmake .. && make

# Finally, run the test and make sure you see the standard GL gears demo
./bin/glfw_test
```
