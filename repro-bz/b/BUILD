load("@npm_ts//@bazel/typescript:index.bzl", "ts_config", "ts_project")
load("@build_bazel_rules_nodejs//:index.bzl", "js_library", "nodejs_binary", "pkg_npm")

package(default_visibility = ["//visibility:public"])

ts_project(
    name = "lib_compile",
    tsconfig = {
        "compilerOptions": {
            "declaration": True,
            "composite": True
        },
    },
    extends = "//repro-bz:tsconfig",
    srcs = [ ":lib.ts" ],
    deps = [ "@npm_ts//fp-ts" ]
)

js_library(
    name = "lib",
    package_name = "ts_project_lib",
    srcs = ["package.json"],
    deps = [":lib_compile"]
)