# Google Colab CLI for Android (Termux)

This repository contains a modified version of the official Google Colab CLI that can be installed and used on Android via Termux.

## Origin

Original project:
https://github.com/googlecolab/google-colab-cli

This version improves Android/Termux compatibility while preserving the original CLI behavior as closely as possible.

All credits for the original project belong to the Google Colab CLI developers.

## Installation

1. Extract the archive.

2. Open a terminal and enter the extracted directory.

3. Install:

```bash
pip install . --break-system-packages
```

4. Verify:

```bash
colab --help
```

## Test

Run compatibility tests:

```bash
colab test
```

Test each component separately:

```bash
colab test environment
colab test notebook
colab test models
colab test kernel-codec
```

For a live Colab kernel test:

```bash
colab new -s android-test
colab test kernel -s android-test
```

For the live T4 SSH/GPU test:

```bash
RUN_GPU_SSH_E2E=1 bash integration/repro_ssh_gpu/test.sh
```

## Notes

- Tested on Termux.
- Python 3.14.
- Android-compatible dependency replacements are used where needed.
- SSH GPU library environment support is included for T4 runtimes.

## Update

26/9/2026:

- Previous version: `0.7.2.post0+android4`
- Current version: `0.7.2.post0+android5.1`
