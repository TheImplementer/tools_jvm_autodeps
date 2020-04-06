java_library(
    name = "grpc_context",
    visibility = [
        "//visibility:public",
    ],
    exports = [
        "//external:jar/io/grpc/grpc_context",
    ],
)

java_library(
    name = "grpc_core",
    visibility = [
        "//visibility:public",
    ],
    exports = [
        "//external:jar/io/grpc/grpc_core",
    ],
    runtime_deps = [
        ":grpc_context",
        "//thirdparty/jvm/com/google/code/gson",
        "//thirdparty/jvm/com/google/errorprone:error_prone_annotations",
        "//thirdparty/jvm/com/google/guava",
        "//thirdparty/jvm/io/opencensus:opencensus_api",
        "//thirdparty/jvm/io/opencensus:opencensus_contrib_grpc_metrics",
        "@maven//:com_google_code_findbugs_jsr305",
    ],
)

java_library(
    name = "grpc_netty",
    visibility = [
        "//visibility:public",
    ],
    exports = [
        "//external:jar/io/grpc/grpc_netty",
    ],
    runtime_deps = [
        ":grpc_core",
        "//thirdparty/jvm/io/netty:netty_codec_http2",
        "//thirdparty/jvm/io/netty:netty_handler_proxy",
    ],
)

java_library(
    name = "grpc_protobuf",
    visibility = [
        "//visibility:public",
    ],
    exports = [
        "//external:jar/io/grpc/grpc_protobuf",
    ],
    runtime_deps = [
        ":grpc_core",
        ":grpc_protobuf_lite",
        "//thirdparty/jvm/com/google/api/grpc:proto_google_common_protos",
        "//thirdparty/jvm/com/google/guava",
        "//thirdparty/jvm/com/google/protobuf:protobuf_java",
        "//thirdparty/jvm/com/google/protobuf:protobuf_java_util",
    ],
)

java_library(
    name = "grpc_protobuf_lite",
    visibility = [
        "//visibility:public",
    ],
    exports = [
        "//external:jar/io/grpc/grpc_protobuf_lite",
    ],
)

java_library(
    name = "grpc_services",
    visibility = [
        "//visibility:public",
    ],
    exports = [
        "//external:jar/io/grpc/grpc_services",
    ],
    runtime_deps = [
        ":grpc_protobuf",
        ":grpc_stub",
        "//thirdparty/jvm/com/google/instrumentation:instrumentation_api",
    ],
)

java_library(
    name = "grpc_stub",
    visibility = [
        "//visibility:public",
    ],
    exports = [
        "//external:jar/io/grpc/grpc_stub",
    ],
    runtime_deps = [
        ":grpc_core",
    ],
)
