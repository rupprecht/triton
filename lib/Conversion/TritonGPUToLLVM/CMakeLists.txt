add_mlir_conversion_library(TritonGPUToLLVM
    TritonGPUToLLVM.cpp
    GCNAsmFormat.cpp
    PTXAsmFormat.cpp
    TritonGPUToLLVMPass.cpp
    ConvertLayoutOpToLLVM/SharedToDotOperandFMA.cpp
    ConvertLayoutOpToLLVM/SharedToDotOperandMMAv1.cpp
    ConvertLayoutOpToLLVM/SharedToDotOperandMMAv2.cpp
    ConvertLayoutOpToLLVM.cpp
    DotOpToLLVM/FMA.cpp
    DotOpToLLVM/MMAv1.cpp
    DotOpToLLVM/MMAv2.cpp
    DotOpToLLVM.cpp
    ElementwiseOpToLLVM.cpp
    LoadStoreOpToLLVM.cpp
    TritonGPUToLLVM.cpp
    TritonGPUToLLVMPass.cpp
    PTXAsmFormat.cpp
    ReduceOpToLLVM.cpp
    ScanOpToLLVM.cpp
    Utility.cpp
    TypeConverter.cpp
    ViewOpToLLVM.cpp

    ADDITIONAL_HEADER_DIRS
    ${PROJECT_SOURCE_DIR}/include/triton/Conversion/TritonGPUToLLVM
    ${PROJECT_BINARY_DIR}/include/triton/Conversion/TritonGPUToLLVM

    DEPENDS
    TritonGPUConversionPassIncGen

    LINK_COMPONENTS
    Core

    LINK_LIBS PUBLIC
    MLIRIR
    MLIRPass
    MLIRGPUDialect
    MLIRGPUToNVVMTransforms
    MLIRGPUToROCDLTransforms
    MLIRGPUTransforms
    TritonAnalysis
    TritonIR
    TritonGPUIR
    TritonGPUTransforms
)
