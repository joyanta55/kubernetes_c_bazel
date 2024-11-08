load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
http_archive(
    name = "rules_foreign_cc",
    sha256 = "a2e6fb56e649c1ee79703e99aa0c9d13c6cc53c8d7a0cbb8797ab2888bbc99a3",
    strip_prefix = "rules_foreign_cc-0.12.0",
    url = "https://github.com/bazelbuild/rules_foreign_cc/releases/download/0.12.0/rules_foreign_cc-0.12.0.tar.gz",
)

load("@rules_foreign_cc//foreign_cc:repositories.bzl", "rules_foreign_cc_dependencies")

# This sets up some common toolchains for building targets. For more details, please see
# https://bazelbuild.github.io/rules_foreign_cc/0.12.0/flatten.html#rules_foreign_cc_dependencies
rules_foreign_cc_dependencies()

load("@bazel_features//:deps.bzl", "bazel_features_deps")

bazel_features_deps()


http_archive(
    name = "kubernetes_c_client",
    sha256 = "10d0c5af1a52a1d2da379e8e45b53978b9dedc90ff195bdff171ae17c1f1dd50",
    strip_prefix = "c-0.11.0",
    url = "https://github.com/kubernetes-client/c/archive/refs/tags/v0.11.0.zip",
    build_file = "@//:libkubec.BUILD",
)
