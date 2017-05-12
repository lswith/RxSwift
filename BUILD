package(default_visibility = ["//visibility:public"])
load("@build_bazel_rules_apple//apple:swift.bzl", "swift_library")

#objc_framework(
#    name = "RxCocoa",
#    framework_imports = [
#        "Carthage/Build/iOS/RxCocoa.framework"
#    ],
#    is_dynamic = 1,
#)

swift_library(
    name = "RxCocoa",
    srcs = glob([
        "RxCocoa/*.swift",
        "RxCocoa/Common/**/*.swift",
        "RxCocoa/Traits/**/*.swift",
        "RxCocoa/Foundation/**/*.swift",
        "RxCocoa/Runtime/**/*.swift",
        "Platform/**/*.swift",
        "RxCocoa/iOS/**/*.swift",
    ],exclude = [
        "RxCocoa/Platform/**/*.swift",
    ]),
    module_name = "RxCocoa",
    deps = [
        "@RxSwift//:RxSwift",
        ":RxCocoaRuntime",
    ]
)

objc_library(
    name = "RxCocoaRuntime",
    srcs = glob([
        "RxCocoa/Common/**/*.m",
        "RxCocoa/Traits/**/*.m",
        "RxCocoa/Foundation/**/*.m",
        "RxCocoa/Runtime/**/*.m",
    ]),
    hdrs = glob([
        "RxCocoa/RxCocoa.h",
        "RxCocoa/Common/**/*.h",
        "RxCocoa/Traits/**/*.h",
        "RxCocoa/Foundation/**/*.h",
        "RxCocoa/Runtime/**/*.h",
    ]),
    includes = [
        "RxCocoa/Runtime/",
        "RxCocoa/Runtime/include/",
    ]
)
