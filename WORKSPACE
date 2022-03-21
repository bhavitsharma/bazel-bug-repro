workspace(name = "relicx")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive", "http_file")

http_archive(
    name = "build_bazel_rules_nodejs",
    sha256 = "3ceb1e5b5dcad5fa2ad8870a20201cfbb9c9c63cac4055c9ab370034c765297f",
    urls = ["https://github.com/bazelbuild/rules_nodejs/releases/download/5.3.0/rules_nodejs-5.3.0.tar.gz"],
)

load("@build_bazel_rules_nodejs//:repositories.bzl", "build_bazel_rules_nodejs_dependencies")

build_bazel_rules_nodejs_dependencies()

load("@build_bazel_rules_nodejs//:index.bzl", "npm_install")

load("@rules_nodejs//nodejs:repositories.bzl", "nodejs_register_toolchains")

_NODE_REPO = "node15"

nodejs_register_toolchains(
    name = _NODE_REPO,
    node_version = "15.14.0",
)

npm_install(
    name = "npm_ts",
    node_repository = _NODE_REPO,
    package_json = "//:package.json",
    package_lock_json = "//:package-lock.json",
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
http_archive(
    name = "bazel_skylib",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-skylib/releases/download/1.2.0/bazel-skylib-1.2.0.tar.gz",
        "https://github.com/bazelbuild/bazel-skylib/releases/download/1.2.0/bazel-skylib-1.2.0.tar.gz",
    ],
    sha256 = "af87959afe497dc8dfd4c6cb66e1279cb98ccc84284619ebfec27d9c09a903de",
)
load("@bazel_skylib//:workspace.bzl", "bazel_skylib_workspace")
bazel_skylib_workspace()