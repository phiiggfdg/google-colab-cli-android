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

For a live Colab kernel test:

```bash
colab new -s android-test
colab test kernel -s android-test
```

For the live T4 SSH/GPU test:

```bash
RUN_GPU_SSH_E2E=1 bash integration/repro_ssh_gpu/test.sh
```

For `colab run` regression tests:

```bash
bash integration/repro_run_command/test.sh
```

For runtime-proxy refresh/recovery:

```bash
bash integration/repro_runtime_proxy_refresh/test.sh
```

## Notes

- Tested on Termux.
- Python 3.14.
- Live T4 GPU SSH access tested successfully.
- `colab run` supports both Python scripts and `.ipynb` notebooks.
- Runtime-proxy credentials are refreshed for long-lived sessions.
- Existing upstream CLI behavior is preserved where possible.

## Update

26/9/2026:

- Previous version: `0.7.2.post0+android5.2`
- Current version: `0.7.2.post0+android5.3`

### Fixed

- Fixed T4 GPU libraries not being visible inside SSH sessions.
- Fixed integration test execution on Termux/Python 3.14.
- Added `.ipynb` support to `colab run`.
- Preserved notebook cell state and saved executed notebook outputs.
- Fixed stale runtime-proxy credentials in long-lived sessions.
- Prevented live sessions from being pruned when runtime-proxy requests return stale 401/404 responses.
- Added live recovery tests for file access and session credential refresh.
