package(default_visibility = [
    "//grpcloader:__subpackages__",
])

java_binary(
    name = "GrpcLocalServer",
    srcs = ["GrpcLocalServer.java"],
    deps = [
        ":BazelPackageLoaderFactory",
        ":Lib",
        ":OperatingSystem",
        ":PackageLoaderFactory",
        ":Serializer",
        "//java/com/google/devtools/javatools/jade/pkgloader/services_proto:services_java_grpc",
        "//java/com/google/devtools/javatools/jade/pkgloader/services_proto:services_java_proto",
        "@io_bazel//src/main/java/com/google/devtools/build/lib:events",
        "@io_bazel//src/main/java/com/google/devtools/build/lib:packages",
        "@io_bazel//src/main/java/com/google/devtools/build/lib:unix",
        "@io_bazel//src/main/java/com/google/devtools/build/lib/skyframe/packages",
        "@io_bazel//src/main/java/com/google/devtools/build/lib/vfs",
        "@maven//:args4j_args4j",
        "@maven//:com_google_guava_guava",
        "@maven//:io_grpc_grpc_core",
        "@maven//:io_grpc_grpc_netty",
        "@maven//:io_grpc_grpc_services",
        "@maven//:io_grpc_grpc_stub",
        "@maven//:io_netty_netty_all",
    ],
)

java_library(
    name = "Lib",
    srcs = ["Lib.java"],
    deps = [
        ":PackageLoaderFactory",
        ":Serializer",
        "//java/com/google/devtools/javatools/jade/pkgloader/services_proto:services_java_proto",
        "@io_bazel//src/main/java/com/google/devtools/build/lib:events",
        "@io_bazel//src/main/java/com/google/devtools/build/lib:packages",
        "@io_bazel//src/main/java/com/google/devtools/build/lib/skyframe/packages",
        "@io_bazel//src/main/java/com/google/devtools/build/lib/vfs",
        "@maven//:com_google_guava_guava",
    ],
)

java_library(
    name = "Serializer",
    srcs = ["Serializer.java"],
    deps = [
        "//java/com/google/devtools/javatools/jade/pkgloader/messages_proto:messages_java_proto",
        "@io_bazel//src/main/java/com/google/devtools/build/lib:packages",
        "@maven//:com_google_guava_guava",
    ],
)

java_library(
    name = "PackageLoaderFactory",
    srcs = ["PackageLoaderFactory.java"],
    deps = [
        "@io_bazel//src/main/java/com/google/devtools/build/lib/skyframe/packages",
        "@io_bazel//src/main/java/com/google/devtools/build/lib/vfs",
    ],
)

java_library(
    name = "BazelPackageLoaderFactory",
    srcs = ["BazelPackageLoaderFactory.java"],
    deps = [
        ":PackageLoaderFactory",
        "@io_bazel//src/main/java/com/google/devtools/build/lib:events",
        "@io_bazel//src/main/java/com/google/devtools/build/lib/skyframe/packages",
        "@io_bazel//src/main/java/com/google/devtools/build/lib/vfs",
        "@maven//:com_google_guava_guava",
    ],
)

java_library(
    name = "OperatingSystem",
    srcs = ["OperatingSystem.java"],
)
