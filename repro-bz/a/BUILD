load("@npm_ts//@bazel/typescript:index.bzl", "ts_config", "ts_project")
load("@build_bazel_rules_nodejs//:index.bzl", "js_library", "nodejs_binary", "pkg_npm")

package(default_visibility = ["//visibility:public"])

ts_project(
    tsconfig = {
        "compilerOptions": {
            "composite": True,
            "declaration": True
        },
    },
    extends = "//repro-bz:tsconfig",
    deps = ["//repro-bz/b:lib"],
    srcs = [ ":lib.ts" ],
    name = "a"
)

nodejs_binary(
    name = "a_bin",
    entry_point = ":lib.ts",
    data = [ ":a" ]
)
