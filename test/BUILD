# copybara:uncomment_begin
# load("//third_party/llvm/build_defs:lit.bzl", "glob_lit_tests")
# load("//tools/build_defs/build_test:build_test.bzl", "build_test")
# 
# package(
#     default_applicable_licenses = ["//:license"],
#     default_compatible_with = ["//buildenv/target:gce"],
#     default_visibility = ["//:__subpackages__"],
# )
# 
# glob_lit_tests(
#     data = [
#         "@llvm-project//llvm:FileCheck",
#         "//:triton-opt",
#     ],
#     driver = "@llvm-project//mlir:run_lit.sh",
#     exclude = [
#         # These require adjusted RUN commands for python internally.
#         "Target/tritongpu_to_llvmir_noinline.mlir",
#         "Target/tritongpu_to_llvmir.mlir",
#         "Target/tritongpu_to_ptx.mlir",
#         # TODO(b/283035396): broken because pattern is disabled by cl532546169.patch.
#         "TritonGPU/dot-operands.mlir",
#     ],
#     test_file_exts = ["mlir"],
# )
# 
# build_test(
#     name = "build_test",
#     allow_empty_target = False,
#     targets = [
#         "//:TritonAnalysis",
#         "//:TritonDialects",
#         "//:TritonGPUToLLVM",
#         "//:TritonGPUTransforms",
#         "//:TritonLLVMIR",
#         "//:TritonPTX",
#         "//:TritonToTritonGPU",
#         "//:TritonTools",
#         "//:TritonTransforms",
#         "//:triton-opt",
#         "//:triton-translate",
#     ],
# )
# copybara:uncomment_end

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
        "//:TritonAnalysis",
        "//:TritonDialects",
    ],
)
