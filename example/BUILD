load("@rules_cc//cc:defs.bzl", "cc_binary")
load("@rules_foreign_cc//foreign_cc:defs.bzl", "cmake")
load("@rules_foreign_cc//foreign_cc:defs.bzl", "make")
cmake(
    name = "kube_c",
    build_args = [
        "--verbose",
        "--",  # <- Pass remaining options to the native tool.
        "-j 1",
    ],
    lib_source = "@kubernetes_c_client//:kubernetes",
    out_shared_libs = ["libkubernetes.so"],
)

cc_binary(
    name = "create_pod",
    srcs = ["create_pod.c"],
    deps = [":kube_c"],
)

cc_binary(
    name = "list_pod",
    srcs = ["list_pod.c"],
    deps = [":kube_c"],
)
