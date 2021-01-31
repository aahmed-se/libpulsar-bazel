workspace(name = "libpulsar")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "new_git_repository")

http_archive(
    name = "com_google_protobuf",
    sha256 = "cfcba2df10feec52a84208693937c17a4b5df7775e1635c1e3baffc487b24c9b",
    strip_prefix = "protobuf-3.9.2",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/protocolbuffers/protobuf/archive/v3.9.2.zip",
        "https://github.com/protocolbuffers/protobuf/archive/v3.9.2.zip",
    ],
)

http_archive(
    name = "boost",
    build_file = "//third_party:boost.BUILD",
    sha256 = "c66e88d5786f2ca4dbebb14e06b566fb642a1a6947ad8cc9091f9f445134143f",
    strip_prefix = "boost_1_72_0",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/dl.bintray.com/boostorg/release/1.72.0/source/boost_1_72_0.tar.gz",
        "https://storage.googleapis.com/mirror.tensorflow.org/downloads.sourceforge.net/project/boost/boost/1.72.0/boost_1_72_0.tar.gz",
        "https://dl.bintray.com/boostorg/release/1.72.0/source/boost_1_72_0.tar.gz",
        "https://downloads.sourceforge.net/project/boost/boost/1.72.0/boost_1_72_0.tar.gz",
    ],
)

http_archive(
    name = "zlib",
    build_file = "//third_party:zlib.BUILD",
    sha256 = "c3e5e9fdd5004dcb542feda5ee4f0ff0744628baf8ed2dd5d66f8ca1197cb1a1",
    strip_prefix = "zlib-1.2.11",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/zlib.net/zlib-1.2.11.tar.gz",
        "https://zlib.net/zlib-1.2.11.tar.gz",
    ],
)

http_archive(
    name = "zstd",
    build_file = "//third_party:zstd.BUILD",
    sha256 = "a364f5162c7d1a455cc915e8e3cf5f4bd8b75d09bc0f53965b0c9ca1383c52c8",
    strip_prefix = "zstd-1.4.4",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/facebook/zstd/archive/v1.4.4.tar.gz",
        "https://github.com/facebook/zstd/archive/v1.4.4.tar.gz",
    ],
)

http_archive(
    name = "lz4",
    build_file = "//third_party:lz4.BUILD",
    sha256 = "658ba6191fa44c92280d4aa2c271b0f4fbc0e34d249578dd05e50e76d0e5efcc",
    strip_prefix = "lz4-1.9.2",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/lz4/lz4/archive/v1.9.2.tar.gz",
        "https://github.com/lz4/lz4/archive/v1.9.2.tar.gz",
    ],
)

http_archive(
    name = "brotli",
    build_file = "//third_party:brotli.BUILD",
    sha256 = "4c61bfb0faca87219ea587326c467b95acb25555b53d1a421ffa3c8a9296ee2c",
    strip_prefix = "brotli-1.0.7",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/google/brotli/archive/v1.0.7.tar.gz",
        "https://github.com/google/brotli/archive/v1.0.7.tar.gz",
    ],
)

http_archive(
    name = "snappy",
    build_file = "//third_party:snappy.BUILD",
    sha256 = "16b677f07832a612b0836178db7f374e414f94657c138e6993cbfc5dcc58651f",
    strip_prefix = "snappy-1.1.8",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/google/snappy/archive/1.1.8.tar.gz",
        "https://github.com/google/snappy/archive/1.1.8.tar.gz",
    ],
)

http_archive(
    name = "kafka",
    build_file = "//third_party:kafka.BUILD",
    patch_cmds = [
        "rm -f src/win32_config.h",
        # TODO: Remove the fowllowing once librdkafka issue is resolved.
        """sed -i.bak '\\|rd_kafka_log(rk,|,/ exceeded);/ s/^/\\/\\//' src/rdkafka_cgrp.c""",
    ],
    sha256 = "f7fee59fdbf1286ec23ef0b35b2dfb41031c8727c90ced6435b8cf576f23a656",
    strip_prefix = "librdkafka-1.5.0",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/edenhill/librdkafka/archive/v1.5.0.tar.gz",
        "https://github.com/edenhill/librdkafka/archive/v1.5.0.tar.gz",
    ],
)

http_archive(
    name = "dcmtk",
    build_file = "//third_party:dcmtk.BUILD",
    sha256 = "a05178665f21896dbb0974106dba1ad144975414abd760b4cf8f5cc979f9beb9",
    strip_prefix = "dcmtk-3.6.5",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/dicom.offis.de/download/dcmtk/dcmtk365/dcmtk-3.6.5.tar.gz",
        "https://dicom.offis.de/download/dcmtk/dcmtk365/dcmtk-3.6.5.tar.gz",
    ],
)

http_archive(
    name = "boringssl",
    patch_cmds = [
        """sed -i.bak 's/bio.c",/bio.c","src\\/decrepit\\/bio\\/base64_bio.c",/g' BUILD.generated.bzl""",
    ],
    sha256 = "1188e29000013ed6517168600fc35a010d58c5d321846d6a6dfee74e4c788b45",
    strip_prefix = "boringssl-7f634429a04abc48e2eb041c81c5235816c96514",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/google/boringssl/archive/7f634429a04abc48e2eb041c81c5235816c96514.tar.gz",
        "https://github.com/google/boringssl/archive/7f634429a04abc48e2eb041c81c5235816c96514.tar.gz",
    ],
)

http_archive(
    name = "curl",
    build_file = "//third_party:curl.BUILD",
    sha256 = "01ae0c123dee45b01bbaef94c0bc00ed2aec89cb2ee0fd598e0d302a6b5e0a98",
    strip_prefix = "curl-7.69.1",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/curl.haxx.se/download/curl-7.69.1.tar.gz",
        "https://curl.haxx.se/download/curl-7.69.1.tar.gz",
    ],
)

http_archive(
    name = "xz",
    build_file = "//third_party:xz.BUILD",
    sha256 = "b512f3b726d3b37b6dc4c8570e137b9311e7552e8ccbab4d39d47ce5f4177145",
    strip_prefix = "xz-5.2.4",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/tukaani.org/xz/xz-5.2.4.tar.gz",
        "https://tukaani.org/xz/xz-5.2.4.tar.gz",
    ],
)

http_archive(
    name = "rules_python",
    sha256 = "c911dc70f62f507f3a361cbc21d6e0d502b91254382255309bc60b7a0f48de28",
    strip_prefix = "rules_python-38f86fb55b698c51e8510c807489c9f4e047480e",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/bazelbuild/rules_python/archive/38f86fb55b698c51e8510c807489c9f4e047480e.tar.gz",
        "https://github.com/bazelbuild/rules_python/archive/38f86fb55b698c51e8510c807489c9f4e047480e.tar.gz",
    ],
)

load("@rules_python//python:pip.bzl", "pip3_import")

# pip3_import(
#     name = "lint_dependencies",
#     requirements = "//tools/lint:requirements.txt",
# )

# load("@lint_dependencies//:requirements.bzl", "pip_install")

# pip_install()

http_archive(
    name = "com_github_grpc_grpc",
    patch_cmds = [
        """sed -i.bak 's/"python",/"python3",/g' third_party/py/python_configure.bzl""",
        """sed -i.bak 's/PYTHONHASHSEED=0/PYTHONHASHSEED=0 python3/g' bazel/cython_library.bzl""",
    ],
    sha256 = "b956598d8cbe168b5ee717b5dafa56563eb5201a947856a6688bbeac9cac4e1f",
    strip_prefix = "grpc-b54a5b338637f92bfcf4b0bc05e0f57a5fd8fadd",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/grpc/grpc/archive/b54a5b338637f92bfcf4b0bc05e0f57a5fd8fadd.tar.gz",
        "https://github.com/grpc/grpc/archive/b54a5b338637f92bfcf4b0bc05e0f57a5fd8fadd.tar.gz",
    ],
)

load("@com_github_grpc_grpc//bazel:grpc_deps.bzl", "grpc_deps")

grpc_deps()

load("@rules_python//python:pip.bzl", "pip_repositories")

pip3_import(
    name = "grpc_python_dependencies",
    requirements = "@com_github_grpc_grpc//:requirements.bazel.txt",
)

load("@grpc_python_dependencies//:requirements.bzl", "pip_install")

pip_repositories()

pip_install()

# TODO(https://github.com/grpc/grpc/issues/19835): Remove.
load("@upb//bazel:workspace_deps.bzl", "upb_deps")

upb_deps()

load("@build_bazel_rules_apple//apple:repositories.bzl", "apple_rules_dependencies")

apple_rules_dependencies()

load("@build_bazel_apple_support//lib:repositories.bzl", "apple_support_dependencies")

apple_support_dependencies()

http_archive(
    name = "com_github_googleapis_google_cloud_cpp",
    patch_cmds = [
        """sed -i.bak 's/CURL\\* m/CURLM* m/g' google/cloud/storage/internal/curl_handle_factory.cc""",
    ],
    repo_mapping = {
        "@com_github_curl_curl": "@curl",
        "@com_github_nlohmann_json": "@nlohmann_json_lib",
    },
    sha256 = "14bf9bf97431b890e0ae5dca8f8904841d4883b8596a7108a42f5700ae58d711",
    strip_prefix = "google-cloud-cpp-1.21.0",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/googleapis/google-cloud-cpp/archive/v1.21.0.tar.gz",
        "https://github.com/googleapis/google-cloud-cpp/archive/v1.21.0.tar.gz",
    ],
)

http_archive(
    name = "nlohmann_json_lib",
    build_file = "//third_party:nlohmann_json.BUILD",
    sha256 = "c377963a95989270c943d522bfefe7b889ef5ed0e1e15d535fd6f6f16ed70732",
    strip_prefix = "json-3.4.0",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/nlohmann/json/archive/v3.4.0.tar.gz",
        "https://github.com/nlohmann/json/archive/v3.4.0.tar.gz",
    ],
)

http_archive(
    name = "com_google_googleapis",
    build_file = "@com_github_googleapis_google_cloud_cpp//bazel:googleapis.BUILD",
    sha256 = "7ebab01b06c555f4b6514453dc3e1667f810ef91d1d4d2d3aa29bb9fcb40a900",
    strip_prefix = "googleapis-541b1ded4abadcc38e8178680b0677f65594ea6f",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/googleapis/googleapis/archive/541b1ded4abadcc38e8178680b0677f65594ea6f.zip",
        "https://github.com/googleapis/googleapis/archive/541b1ded4abadcc38e8178680b0677f65594ea6f.zip",
    ],
)

load("@com_github_googleapis_google_cloud_cpp//bazel:google_cloud_cpp_deps.bzl", "google_cloud_cpp_deps")

google_cloud_cpp_deps()

load("@com_google_googleapis//:repository_rules.bzl", "switched_rules_by_language")

# Configure @com_google_googleapis to only compile C++ and gRPC:
switched_rules_by_language(
    name = "com_google_googleapis_imports",
    cc = True,  # C++ support is only "Partially implemented", roll our own.
    grpc = True,
)

http_archive(
    name = "com_googlesource_code_re2",
    sha256 = "a31397714a353587413d307337d0b58f8a2e20e2b9d02f2e24e3463fa4eeda81",
    strip_prefix = "re2-2018-10-01",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/google/re2/archive/2018-10-01.tar.gz",
        "https://github.com/google/re2/archive/2018-10-01.tar.gz",
    ],
)

http_archive(
    name = "com_google_googletest",
    sha256 = "9bf1fe5182a604b4135edc1a425ae356c9ad15e9b23f9f12a02e80184c3a249c",
    strip_prefix = "googletest-release-1.8.1",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/google/googletest/archive/release-1.8.1.tar.gz",
        "https://github.com/google/googletest/archive/release-1.8.1.tar.gz",
    ],
)

http_archive(
    name = "libarchive",
    build_file = "//third_party:libarchive.BUILD",
    sha256 = "720da414e7aebb255fcdaee106894e4d30e2472ac1390c2c15b70c84c7479658",
    strip_prefix = "libarchive-3.3.3",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/libarchive/libarchive/archive/v3.3.3.tar.gz",
        "https://github.com/libarchive/libarchive/archive/v3.3.3.tar.gz",
    ],
)

http_archive(
    name = "libexpat",
    build_file = "//third_party:libexpat.BUILD",
    sha256 = "574499cba22a599393e28d99ecfa1e7fc85be7d6651d543045244d5b561cb7ff",
    strip_prefix = "libexpat-R_2_2_6/expat",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/libexpat/libexpat/archive/R_2_2_6.tar.gz",
        "http://github.com/libexpat/libexpat/archive/R_2_2_6.tar.gz",
    ],
)

http_archive(
    name = "libapr1",
    build_file = "//third_party:libapr1.BUILD",
    patch_args = ["-p1"],
    patches = [
        "//third_party:libapr1.patch",
    ],
    sha256 = "096968a363b2374f7450a3c65f3cc0b50561204a8da7bc03a2c39e080febd6e1",
    strip_prefix = "apr-1.6.5",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/apache/apr/archive/1.6.5.tar.gz",
        "https://github.com/apache/apr/archive/1.6.5.tar.gz",
    ],
)

http_archive(
    name = "libaprutil1",
    build_file = "//third_party:libaprutil1.BUILD",
    patch_args = ["-p1"],
    patches = [
        "//third_party:libaprutil1.patch",
    ],
    sha256 = "4c9ae319cedc16890fc2776920e7d529672dda9c3a9a9abd53bd80c2071b39af",
    strip_prefix = "apr-util-1.6.1",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/apache/apr-util/archive/1.6.1.tar.gz",
        "https://github.com/apache/apr-util/archive/1.6.1.tar.gz",
    ],
)

http_archive(
    name = "mxml",
    build_file = "//third_party:mxml.BUILD",
    patch_args = ["-p1"],
    patches = [
        "//third_party:mxml.patch",
    ],
    sha256 = "4d850d15cdd4fdb9e82817eb069050d7575059a9a2729c82b23440e4445da199",
    strip_prefix = "mxml-2.12",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/michaelrsweet/mxml/archive/v2.12.tar.gz",
        "https://github.com/michaelrsweet/mxml/archive/v2.12.tar.gz",
    ],
)

http_archive(
    name = "aliyun_oss_c_sdk",
    build_file = "//third_party:oss_c_sdk.BUILD",
    sha256 = "6450d3970578c794b23e9e1645440c6f42f63be3f82383097660db5cf2fba685",
    strip_prefix = "aliyun-oss-c-sdk-3.7.0",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/aliyun/aliyun-oss-c-sdk/archive/3.7.0.tar.gz",
        "https://github.com/aliyun/aliyun-oss-c-sdk/archive/3.7.0.tar.gz",
    ],
)

http_archive(
    name = "jsoncpp_git",
    build_file = "//third_party:jsoncpp.BUILD",
    sha256 = "c49deac9e0933bcb7044f08516861a2d560988540b23de2ac1ad443b219afdb6",
    strip_prefix = "jsoncpp-1.8.4",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/open-source-parsers/jsoncpp/archive/1.8.4.tar.gz",
        "https://github.com/open-source-parsers/jsoncpp/archive/1.8.4.tar.gz",
    ],
)

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "ae8c36ff6e565f674c7a3692d6a9ea1096e4c1ade497272c2108a810fb39acd2",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/bazelbuild/rules_go/releases/download/0.19.4/rules_go-0.19.4.tar.gz",
        "https://github.com/bazelbuild/rules_go/releases/download/0.19.4/rules_go-0.19.4.tar.gz",
    ],
)

http_archive(
    name = "bazel_gazelle",
    sha256 = "7fc87f4170011201b1690326e8c16c5d802836e3a0d617d8f75c3af2b23180c4",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/bazelbuild/bazel-gazelle/releases/download/0.18.2/bazel-gazelle-0.18.2.tar.gz",
        "https://github.com/bazelbuild/bazel-gazelle/releases/download/0.18.2/bazel-gazelle-0.18.2.tar.gz",
    ],
)

load("@io_bazel_rules_go//go:deps.bzl", "go_register_toolchains", "go_rules_dependencies")

go_rules_dependencies()

go_register_toolchains()

load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies", "go_repository")

gazelle_dependencies()

http_archive(
    name = "nucleus",
    build_file = "//third_party:nucleus.BUILD",
    patch_args = ["-p1"],
    patches = [
        "//third_party:nucleus.patch",
    ],
    sha256 = "aa865d3509ba8f3527392303bd95a11f48f19e68197b3d1d0bae9fab004bee87",
    strip_prefix = "nucleus-0.4.1",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/google/nucleus/archive/0.4.1.tar.gz",
        "https://github.com/google/nucleus/archive/0.4.1.tar.gz",
    ],
)

http_archive(
    name = "bzip2",
    build_file = "//third_party:bzip2.BUILD",
    sha256 = "ab5a03176ee106d3f0fa90e381da478ddae405918153cca248e682cd0c4a2269",
    strip_prefix = "bzip2-1.0.8",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/sourceware.org/pub/bzip2/bzip2-1.0.8.tar.gz",
        "https://sourceware.org/pub/bzip2/bzip2-1.0.8.tar.gz",
    ],
)

http_archive(
    name = "com_googlesource_code_cctz",
    sha256 = "4ee3497b413229083998dd4295fa070b47a7253d88a15306733a06bae15ce945",
    strip_prefix = "cctz-44541cf2b85ced2a6e5ad4276183a9812d1a54ab",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/google/cctz/archive/44541cf2b85ced2a6e5ad4276183a9812d1a54ab.zip",
        "https://github.com/google/cctz/archive/44541cf2b85ced2a6e5ad4276183a9812d1a54ab.zip",
    ],
)

# This is the 1.9 release of htslib.
http_archive(
    name = "htslib",
    build_file = "//third_party:htslib.BUILD",
    sha256 = "c4d3ae84014f8a80f5011521f391e917bc3b4f6ebd78e97f238472e95849ec14",
    strip_prefix = "htslib-1.9",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/samtools/htslib/archive/1.9.zip",
        "https://github.com/samtools/htslib/archive/1.9.zip",
    ],
)

http_archive(
    name = "io_bazel_rules_closure",
    sha256 = "43c9b882fa921923bcba764453f4058d102bece35a37c9f6383c713004aacff1",
    strip_prefix = "rules_closure-9889e2348259a5aad7e805547c1a0cf311cfcd91",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/bazelbuild/rules_closure/archive/9889e2348259a5aad7e805547c1a0cf311cfcd91.tar.gz",  # 2018-12-21
        "https://github.com/bazelbuild/rules_closure/archive/9889e2348259a5aad7e805547c1a0cf311cfcd91.tar.gz",  # 2018-12-21
    ],
)

# bazel_skylib is now a required dependency of protobuf_archive.
http_archive(
    name = "bazel_skylib",
    sha256 = "bbccf674aa441c266df9894182d80de104cabd19be98be002f6d478aaa31574d",
    strip_prefix = "bazel-skylib-2169ae1c374aab4a09aa90e65efe1a3aad4e279b",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/bazelbuild/bazel-skylib/archive/2169ae1c374aab4a09aa90e65efe1a3aad4e279b.tar.gz",
        "https://github.com/bazelbuild/bazel-skylib/archive/2169ae1c374aab4a09aa90e65efe1a3aad4e279b.tar.gz",
    ],
)

http_archive(
    name = "com_grail_bazel_toolchain",
    sha256 = "9e6065ded4b7453143e1586d6819729a63cd233114b72bf85ff3435367b02c90",
    strip_prefix = "bazel-toolchain-edd07e96a2ecaa131af9234d6582875d980c0ac7",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/grailbio/bazel-toolchain/archive/edd07e96a2ecaa131af9234d6582875d980c0ac7.tar.gz",
        "https://github.com/grailbio/bazel-toolchain/archive/edd07e96a2ecaa131af9234d6582875d980c0ac7.tar.gz",
    ],
)

load("@com_grail_bazel_toolchain//toolchain:rules.bzl", "llvm_toolchain")

llvm_toolchain(
    name = "llvm_toolchain",
    llvm_version = "9.0.0",
)

http_archive(
    name = "dlfcn-win32",
    build_file = "//third_party:dlfcn-win32.BUILD",
    sha256 = "f18a412e84d8b701e61a78252411fe8c72587f52417c1ef21ca93604de1b9c55",
    strip_prefix = "dlfcn-win32-1.2.0",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/dlfcn-win32/dlfcn-win32/archive/v1.2.0.tar.gz",
        "https://github.com/dlfcn-win32/dlfcn-win32/archive/v1.2.0.tar.gz",
    ],
)

http_archive(
    name = "pulsar",
    build_file = "//third_party:pulsar.BUILD",
    patch_cmds = [
        "cp pulsar-common/src/main/proto/PulsarApi.proto pulsar-client-cpp/lib",
        "sed -i.bak 's/define PULSAR_DEFINES_H_/define PULSAR_DEFINES_H_\\'$'\\n''#if defined(_MSC_VER)\\'$'\\n''#include <Windows.h>\\'$'\\n''#undef ERROR\\'$'\\n''#endif/g' pulsar-client-cpp/include/pulsar/defines.h",
        "sed -i.bak 's/define LIB_ACKGROUPINGTRACKER_H_/define LIB_ACKGROUPINGTRACKER_H_\\'$'\\n''#include <pulsar\\/defines.h>/g' pulsar-client-cpp/lib/AckGroupingTracker.h",
    ],
    sha256 = "08f19ca6d6353751ff0661403b16b71425bf7ada3d8835a38e426ae303b0e385",
    strip_prefix = "pulsar-2.6.1",
    urls = [
        "https://github.com/apache/pulsar/archive/v2.6.1.tar.gz",
    ],
)
