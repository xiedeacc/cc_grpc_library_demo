workspace(name = "cc_grpc_library_demo")
load(
    "@bazel_tools//tools/build_defs/repo:git.bzl",
    "git_repository",
    "new_git_repository",
)
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

git_repository(
    name = "io_bazel_rules_closure",
    remote = "https://github.com/bazelbuild/rules_closure",
    tag = "0.11.0",
)

git_repository(
    name = "rules_proto",
    commit = "f7a30f6f80006b591fa7c437fe5a951eb10bcbcf",
    remote = "https://github.com/bazelbuild/rules_proto.git",
)

git_repository(
    name = "build_bazel_apple_support",
    remote = "https://github.com/bazelbuild/apple_support.git",
    tag = "0.9.1",
)

load(
    "@build_bazel_apple_support//lib:repositories.bzl",
    "apple_support_dependencies",
)

apple_support_dependencies()

git_repository(
    name = "build_bazel_rules_apple",
    remote = "https://github.com/bazelbuild/rules_apple.git",
    tag = "0.21.2",
)

#apple_rules_dependencies(ignore_version_differences = True)

git_repository(
    name = "rules_java",
    remote = "https://github.com/bazelbuild/rules_java.git",
    tag = "3.7.2",
)

load("@rules_proto//proto:repositories.bzl", "rules_proto_dependencies", "rules_proto_toolchains")

git_repository(
    name = "io_bazel_rules_go",
    remote = "https://github.com/bazelbuild/rules_go.git",
    tag = "v0.25.1",
)

load("@io_bazel_rules_go//go:deps.bzl", "go_register_toolchains", "go_rules_dependencies")

go_rules_dependencies()

go_register_toolchains(version = "1.15.5")

git_repository(
    name = "com_google_protobuf",
    remote = "https://github.com/protocolbuffers/protobuf.git",
    tag = "v3.15.1",
)

git_repository(
    name = "upb",
    commit = "eb0fdda14b7b211872507a66f7d988f7c24a44c9",
    remote = "https://github.com/protocolbuffers/upb.git",
)

git_repository(
    name = "com_github_grpc_grpc",
    remote = "https://github.com/grpc/grpc.git",
    tag = "v1.36.0",
)

git_repository(
    name = "envoy",
    remote = "https://github.com/envoyproxy/envoy.git",
    tag = "v1.17.0",
)

load("@envoy//bazel:api_binding.bzl", "envoy_api_binding")

envoy_api_binding()

load("@envoy//bazel:api_repositories.bzl", "envoy_api_dependencies")

envoy_api_dependencies()

load("@com_github_grpc_grpc//bazel:grpc_deps.bzl", "grpc_deps", "grpc_test_only_deps")
load("@com_github_grpc_grpc//bazel:grpc_extra_deps.bzl", "grpc_extra_deps")

grpc_deps()

grpc_extra_deps()

