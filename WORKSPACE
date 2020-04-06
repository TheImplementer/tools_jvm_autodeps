load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
# Bazel code, required for PackageLoader

http_archive(
    name = "io_bazel",
    sha256 = "724da3c656f68e787a86ebb9844773aa1c2e3a873cc39462a8f1b336153d6cbb",
    urls = ["https://releases.bazel.build/2.0.0/release/bazel-2.0.0-dist.zip"],
)

# Buildozer, to manipulate BUILD files

http_archive(
    name = "com_github_bazelbuild_buildtools",
    strip_prefix = "buildtools-b8569631d3e67c7b83279157dc659903f92e919b",
    type = "zip",
    urls = ["https://github.com/bazelbuild/buildtools/archive/b8569631d3e67c7b83279157dc659903f92e919b.zip"],
)

# Protobuf

# http_archive(
#     name = "com_google_protobuf",
#     sha256 = "f322e5a11bdbf563c2ed5f63020fb0fdaa484a47ffdd41fa89184f5044ad1df9",
#     strip_prefix = "protobuf-3.11.4",
#     type = "zip",
#     urls = ["https://github.com/protocolbuffers/protobuf/releases/download/v3.11.4/protobuf-all-3.11.4.zip"],
# )
http_archive(
    name = "com_google_protobuf",
    strip_prefix = "protobuf-master",
    urls = ["https://github.com/protocolbuffers/protobuf/archive/master.zip"],
)

http_archive(
    name = "rules_cc",
    sha256 = "20e134e1348022090fd38bcf354dd88f4d95808ad905c62cb1a359b03c4ad058",
    strip_prefix = "rules_cc-master",
    urls = ["https://github.com/bazelbuild/rules_cc/archive/master.zip"],
)

http_archive(
    name = "bazel_skylib",
    sha256 = "97e70364e9249702246c0e9444bccdc4b847bed1eb03c5a3ece4f83dfe6abc44",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-skylib/releases/download/1.0.2/bazel-skylib-1.0.2.tar.gz",
        "https://github.com/bazelbuild/bazel-skylib/releases/download/1.0.2/bazel-skylib-1.0.2.tar.gz",
    ],
)

load("@bazel_skylib//:workspace.bzl", "bazel_skylib_workspace")

bazel_skylib_workspace()

# Go - bind external repos

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "142dd33e38b563605f0d20e89d9ef9eda0fc3cb539a14be1bdb1350de2eda659",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_go/releases/download/v0.22.2/rules_go-v0.22.2.tar.gz",
        "https://github.com/bazelbuild/rules_go/releases/download/v0.22.2/rules_go-v0.22.2.tar.gz",
    ],
)

http_archive(
    name = "bazel_gazelle",
    sha256 = "d8c45ee70ec39a57e7a05e5027c32b1576cc7f16d9dd37135b0eddde45cf1b10",
    urls = [
        "https://storage.googleapis.com/bazel-mirror/github.com/bazelbuild/bazel-gazelle/releases/download/v0.20.0/bazel-gazelle-v0.20.0.tar.gz",
        "https://github.com/bazelbuild/bazel-gazelle/releases/download/v0.20.0/bazel-gazelle-v0.20.0.tar.gz",
    ],
)

# gRPC for Go

load("@io_bazel_rules_go//go:deps.bzl", "go_register_toolchains", "go_rules_dependencies")

# Go - load additional repos.

go_rules_dependencies()

go_register_toolchains()

load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies", "go_repository")

gazelle_dependencies()

go_repository(
    name = "org_golang_google_grpc",
    build_file_proto_mode = "disable",  # use existing generated code
    commit = "8e4536a86ab602859c20df5ebfd0bd4228d08655",  # v1.10.0
    importpath = "google.golang.org/grpc",
)

go_repository(
    name = "com_github_google_go_cmp",
    commit = "v0.2.0",
    importpath = "github.com/google/go-cmp",
)

go_repository(
    name = "org_golang_x_net",
    commit = "d3edc9973b7eb1fb302b0ff2c62357091cea9a30",
    importpath = "golang.org/x/net",
)

go_repository(
    name = "org_golang_x_text",
    commit = "06d492aade888ab8698aad35476286b7b555c961",
    importpath = "golang.org/x/text",
)

# Maven jars

RULES_JVM_EXTERNAL_TAG = "3.2"

RULES_JVM_EXTERNAL_SHA = "82262ff4223c5fda6fb7ff8bd63db8131b51b413d26eb49e3131037e79e324af"

http_archive(
    name = "rules_jvm_external",
    sha256 = RULES_JVM_EXTERNAL_SHA,
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)

load("@rules_jvm_external//:defs.bzl", "maven_install")

maven_install(
    artifacts = [
        "args4j:args4j:2.33",
        "com.google.api.grpc:proto-google-common-protos:1.0.0",
        "com.google.code.findbugs:jsr305:3.0.2",
        "com.google.code.gson:gson:2.8.2",
        "com.google.errorprone:error_prone_annotations:2.1.2",
        "com.google.guava:guava:23.0",
        "com.google.instrumentation:instrumentation-api:0.4.3",
        "com.google.j2objc:j2objc-annotations:1.1",
        "com.google.protobuf:protobuf-java-util:3.5.1",
        "com.google.protobuf:protobuf-java:3.5.1",
        "com.google.truth:truth:0.35",
        "io.grpc:grpc-context:1.10.0",
        "io.grpc:grpc-core:1.10.0",
        "io.grpc:grpc-netty:1.10.0",
        "io.grpc:grpc-protobuf-lite:1.10.0",
        "io.grpc:grpc-protobuf:1.10.0",
        "io.grpc:grpc-services:1.10.0",
        "io.grpc:grpc-stub:1.10.0",
        "io.netty:netty-all:4.1.22.Final",
        "io.netty:netty-buffer:4.1.17.Final",
        "io.netty:netty-codec-http2:4.1.17.Final",
        "io.netty:netty-codec-http:4.1.17.Final",
        "io.netty:netty-codec-socks:4.1.17.Final",
        "io.netty:netty-codec:4.1.17.Final",
        "io.netty:netty-common:4.1.17.Final",
        "io.netty:netty-handler-proxy:4.1.17.Final",
        "io.netty:netty-handler:4.1.17.Final",
        "io.netty:netty-resolver:4.1.17.Final",
        "io.netty:netty-transport:4.1.17.Final",
        "io.opencensus:opencensus-api:0.11.0",
        "io.opencensus:opencensus-contrib-grpc-metrics:0.11.0",
        "junit:junit:4.12",
        "org.codehaus.mojo:animal-sniffer-annotations:1.14",
        "org.hamcrest:hamcrest-core:1.3",
        "org.textmapper:lapg:0.9.18",
        "org.textmapper:templates:0.9.18",
        "org.textmapper:textmapper:0.9.18",
    ],
    repositories = [
        "https://jcenter.bintray.com/",
        "https://maven.google.com",
        "https://repo1.maven.org/maven2",
    ],
)

# gRPC for Java

http_archive(
    name = "grpc_java",
    strip_prefix = "grpc-java-1.28.0",
    urls = [
        "https://github.com/grpc/grpc-java/archive/v1.28.0.zip",
    ],
)

load("@grpc_java//:repositories.bzl", "grpc_java_repositories")

grpc_java_repositories()

http_archive(
    name = "rules_proto",
    sha256 = "602e7161d9195e50246177e7c55b2f39950a9cf7366f74ed5f22fd45750cd208",
    strip_prefix = "rules_proto-97d8af4dc474595af3900dd85cb3a29ad28cc313",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_proto/archive/97d8af4dc474595af3900dd85cb3a29ad28cc313.tar.gz",
        "https://github.com/bazelbuild/rules_proto/archive/97d8af4dc474595af3900dd85cb3a29ad28cc313.tar.gz",
    ],
)

load("@rules_proto//proto:repositories.bzl", "rules_proto_dependencies", "rules_proto_toolchains")

rules_proto_dependencies()

rules_proto_toolchains()

http_archive(
    name = "rules_python",
    sha256 = "aa96a691d3a8177f3215b14b0edc9641787abaaa30363a080165d06ab65e1161",
    url = "https://github.com/bazelbuild/rules_python/releases/download/0.0.1/rules_python-0.0.1.tar.gz",
)

load("@rules_python//python:repositories.bzl", "py_repositories")

py_repositories()

# Only needed if using the packaging rules.
load("@rules_python//python:pip.bzl", "pip_repositories")

pip_repositories()

http_archive(
    name = "rules_pkg",
    sha256 = "352c090cc3d3f9a6b4e676cf42a6047c16824959b438895a76c2989c6d7c246a",
    urls = [
        "https://github.com/bazelbuild/rules_pkg/releases/download/0.2.5/rules_pkg-0.2.5.tar.gz",
        "https://mirror.bazel.build/github.com/bazelbuild/rules_pkg/releases/download/0.2.5/rules_pkg-0.2.5.tar.gz",
    ],
)

load("@rules_pkg//:deps.bzl", "rules_pkg_dependencies")

rules_pkg_dependencies()

local_repository(
    name = "googleapis",
    path = "./googledeps/googleapis/",
)

local_repository(
    name = "remoteapis",
    path = "./googledeps/remoteapis/",
)
