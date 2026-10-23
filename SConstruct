import os

triplet = "x64-linux"

vcpkg_root = os.path.abspath(
    os.path.join("vcpkg_installed", triplet),
)

cpp_path = [
    os.path.join(vcpkg_root, "include"),
]

lib_path = [
    os.path.join(vcpkg_root, "lib"),
]

libs = [
    "fmt",
]

# Environment setup
env = Environment(
    CPPPATH=cpp_path,
    LIBPATH=lib_path,
    LIBS=libs,
)

# Compilation database
env.Tool("compilation_db")
env["COMPILATIONDB_USE_ABSPATH"] = True
env.CompilationDatabase("build/compile_commands.json")

SConscript(
    "SConscript",
    variant_dir="build",
    duplicate=0,
    exports={
        "env": env,
    },
)
