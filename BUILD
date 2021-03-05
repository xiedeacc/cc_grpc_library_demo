load("@com_github_grpc_grpc//bazel:cc_grpc_library.bzl", "cc_grpc_library")

package(default_visibility = ["//visibility:public"])
filegroup(
    name = "foo_bar_files",
    srcs = [
        "foo/foo.proto",
        "bar/bar.proto",
    ],
)

proto_library(
    name = "foo_proto",
    srcs = ["foo/foo.proto"],
    deps = [
        ":bar_proto",
    ],
)

proto_library(
    name = "bar_proto",
    srcs = ["bar/bar.proto"],
)

proto_library(
    name = "foo_bar_proto",
    srcs = [
        "bar/bar.proto",
        "foo/foo.proto",
    ],
)

cc_proto_library(
    name = "cc_bar_proto",
    deps = [":bar_proto"],
)

cc_proto_library(
    name = "cc_foo_proto",
    deps = [":foo_proto"],
)

# Works:
cc_grpc_library(
    name = "foo_cc_grpc",
    srcs = [":foo_proto"],
    grpc_only = True,
    deps = [
        ":cc_bar_proto",
        ":cc_foo_proto",
    ],
)
