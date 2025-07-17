[![CI](https://github.com/allyourcodebase/libarchive/actions/workflows/ci.yaml/badge.svg)](https://github.com/allyourcodebase/libarchive/actions)

# libarchive

This is [libarchive](ttps://github.com/libarchive/libarchive), packaged for [Zig](https://ziglang.org/).

## Installation

First, update your `build.zig.zon`:

```
# Initialize a `zig build` project if you haven't already
zig init
zig fetch --save git+https://github.com/allyourcodebase/libarchive.git#3.8.1
```

You can then import `libarchive` in your `build.zig` with:

```zig
const bzip_dependency = b.dependency("libarchive", .{
    .target = target,
    .optimize = optimize,
});
your_exe.linkLibrary(bzip_dependency.artifact("archive"));
```

## Note
Cross compiling to MacOS requires CoreServices.
