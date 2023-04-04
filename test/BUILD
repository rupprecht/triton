load("//third_party/llvm/build_defs:lit.bzl", "glob_lit_tests")
load("//tools/build_defs/build_test:build_test.bzl", "build_test")

package(
    default_compatible_with = ["//buildenv/target:gce"],
    default_visibility = ["//third_party/triton:__subpackages__"],
)

glob_lit_tests(
    data = [
        "@llvm-project//llvm:FileCheck",
        "//third_party/triton:triton-opt",
    ],
    driver = "@llvm-project//mlir:run_lit.sh",
    exclude = [
        # These require adjusted RUN commands for python in google3.
        "Target/tritongpu_to_llvmir.mlir",
        "Target/tritongpu_to_ptx.mlir",
    ],
    test_file_exts = ["mlir"],
)

cc_library(
    name = "TritonTestAnalysis",
    srcs = glob(["lib/Analysis/*.cpp"]),
    deps = [
        "@llvm-project//mlir:Analysis",
        "@llvm-project//mlir:GPUDialect",
        "@llvm-project//mlir:IR",
        "@llvm-project//mlir:Pass",
        "@llvm-project//mlir:SCFToControlFlow",
        "@llvm-project//mlir:Transforms",
        "//third_party/triton:TritonAnalysis",
        "//third_party/triton:TritonGPUDialect",
    ],
)

build_test(
    name = "build_test",
    allow_empty_target = False,
    targets = [
        "//third_party/triton:TritonAnalysis",
        "//third_party/triton:TritonDialect",
        "//third_party/triton:TritonGPUDialect",
        "//third_party/triton:TritonGPUToLLVM",
        "//third_party/triton:TritonGPUTransforms",
        "//third_party/triton:TritonLLVMIR",
        "//third_party/triton:TritonPTX",
        "//third_party/triton:TritonToTritonGPU",
        "//third_party/triton:TritonTools",
        "//third_party/triton:TritonTransforms",
        "//third_party/triton:triton-opt",
        "//third_party/triton:triton-translate",
    ],
)
