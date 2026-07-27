# Google Colab CLI for Android (Termux)

This repository contains a modified version of the official Google Colab CLI that can be installed and used on Android via Termux.

## Origin

Original project:
https://github.com/google/google-colab-cli

This version replaces the Android-incompatible components with a pure Python implementation so it can be installed successfully on Termux.

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

## Notes

- Tested on Termux.
- Python 3.14.
- This repository is intended to improve Android compatibility while preserving the original CLI functionality.
