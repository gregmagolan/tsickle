workspace(name="tsickle")

http_archive(
    name = "build_bazel_rules_nodejs",
    url = "https://github.com/gregmagolan/rules_nodejs/archive/d450dbff75a1a6a0833a643c6ffb9731293258dd.zip",
    strip_prefix = "rules_nodejs-d450dbff75a1a6a0833a643c6ffb9731293258dd",
    sha256 = "9f230129c813b55289051f25e09a763a40994cb95c4bbc36484a98d8adf156b3",
)

load("@build_bazel_rules_nodejs//:defs.bzl", "check_bazel_version", "node_repositories")

# Force developers to use the same Bazel version as Travis,
# to prevent different local behavior than CI.
# See travis_install.sh
check_bazel_version("0.9.0")

# NOTE: this rule installs nodejs, npm, and yarn, but does NOT install
# your npm dependencies. You must still run the package manager.
node_repositories(package_json = [
    # Install TS 2.4 + 2.5 first, since the other package.json relies on it
    # in order to build its sources.
    "//test_ts24:package.json",
    "//test_ts25:package.json",
    "//test_ts26:package.json",
    "//test_ts27:package.json",
    "//:package.json",
])

http_archive(
    name = "io_bazel_rules_webtesting",
    url = "https://github.com/bazelbuild/rules_webtesting/archive/v0.2.0.zip",
    strip_prefix = "rules_webtesting-0.2.0",
    sha256 = "cecc12f07e95740750a40d38e8b14b76fefa1551bef9332cb432d564d693723c",
)

http_archive(
    name = "build_bazel_rules_typescript",
    url = "https://github.com/bazelbuild/rules_typescript/archive/0.15.0.zip",
    strip_prefix = "rules_typescript-0.15.0",
    sha256 = "1aa75917330b820cb239b3c10a936a10f0a46fe215063d4492dd76dc6e1616f4",
)

load("@build_bazel_rules_typescript//:defs.bzl", "ts_setup_workspace")

ts_setup_workspace()
