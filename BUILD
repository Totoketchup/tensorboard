# Description:
# TensorBoard, a dashboard for investigating TensorFlow

package(default_visibility = ["//tensorflow:internal"])

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

filegroup(
    name = "frontend",
    srcs = [
        "dist/index.html",
        "dist/tf-tensorboard.html",
        "//tensorflow/tensorboard/bower:bower",
        "TAG",
    ] + glob(["lib/**/*"]),
)


py_binary(
    name = "tensorboard",
    srcs = ["tensorboard.py"],
    data = [":frontend"],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/tensorboard/backend:server",
        "//tensorflow/python:platform",
    ],
)

filegroup(
    name = "all_files",
    srcs = glob(
        ["**/*"],
        exclude = [
            "**/METADATA",
            "**/OWNERS",
            "**/node_modules/**",
            "**/typings/**",
        ],
    ),
    visibility = ["//tensorflow:__subpackages__"],
)
