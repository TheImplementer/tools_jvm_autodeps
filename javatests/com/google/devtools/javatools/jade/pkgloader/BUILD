java_test(
    name = "SerializerTest",
    srcs = ["SerializerTest.java"],
    deps = [
        ":MockWorkspace",
        "//java/com/google/devtools/javatools/jade/pkgloader:BazelPackageLoaderFactory",
        "//java/com/google/devtools/javatools/jade/pkgloader:PackageLoaderFactory",
        "//java/com/google/devtools/javatools/jade/pkgloader:Serializer",
        "//java/com/google/devtools/javatools/jade/pkgloader/messages_proto:messages_java_proto",
        "@io_bazel//src/main/java/com/google/devtools/build/lib:packages",
        "@io_bazel//src/main/java/com/google/devtools/build/lib/skyframe/packages",
        "@io_bazel//src/main/java/com/google/devtools/build/lib/vfs/inmemoryfs",
        "@maven//:com_google_guava_guava",
        "@maven//:com_google_truth_truth",
        "@maven//:junit_junit",
    ],
)

java_test(
    name = "BazelPackageLoaderFactoryTest",
    srcs = ["BazelPackageLoaderFactoryTest.java"],
    deps = [
        "//java/com/google/devtools/javatools/jade/pkgloader:BazelPackageLoaderFactory",
        "@maven//:junit_junit",
    ],
)

java_test(
    name = "LibTest",
    srcs = ["LibTest.java"],
    deps = [
        ":MockWorkspace",
        "//java/com/google/devtools/javatools/jade/pkgloader:BazelPackageLoaderFactory",
        "//java/com/google/devtools/javatools/jade/pkgloader:Lib",
        "//java/com/google/devtools/javatools/jade/pkgloader:PackageLoaderFactory",
        "//java/com/google/devtools/javatools/jade/pkgloader/services_proto:services_java_proto",
        "@io_bazel//src/main/java/com/google/devtools/build/lib/vfs",
        "@io_bazel//src/main/java/com/google/devtools/build/lib/vfs/inmemoryfs",
        "@maven//:com_google_truth_truth",
        "@maven//:junit_junit",
    ],
)

java_library(
    name = "MockWorkspace",
    srcs = ["MockWorkspace.java"],
    deps = [
        "@io_bazel//src/main/java/com/google/devtools/build/lib/vfs",
    ],
)
