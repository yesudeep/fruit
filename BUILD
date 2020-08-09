load("@rules_cc//cc:defs.bzl", "cc_library")

package(default_visibility = ["//visibility:public"])

licenses(["notice"])  # Apache version 2.0

exports_files(["COPYING"])

filegroup(
    name = "fruit_headers",
    srcs = glob([
        "include/**/*.h",
    ]) + [
        "//third_party/fruit/configuration/bazel:fruit_config",
    ],
)

cc_library(
    name = "fruit",
    srcs = glob([
        "src/*.cpp",
        "include/fruit/impl/**/*.h",
    ]) + ["//third_party/fruit/configuration/bazel:fruit_config"],
    hdrs = glob(["include/fruit/*.h"]),
    includes = [
        "configuration/bazel",
        "include",
    ],
    linkopts = ["-lm"],
    deps = [
        "@boost//:unordered",
    ],
)
