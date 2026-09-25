Google Colab CLI for Android (Termux)

This repository contains a modified version of the official Google Colab CLI that can be installed and used on Android via Termux.

Origin

Original project:
https://github.com/googlecolab/google-colab-cli

This version replaces the Android-incompatible components with a pure Python implementation so it can be installed successfully on Termux.

All credits for the original project belong to the Google Colab CLI developers.

Installation

1. Extract the archive.

2. Open a terminal and enter the extracted directory.

3. Install:

pip install . --break-system-packages

4. Verify:

colab --help

Test

Run compatibility tests:

colab test

Test each component separately:

colab test environment
colab test notebook
colab test models
colab test kernel-codec

For a live Colab kernel test:

colab new -s android-test
colab test kernel -s android-test

Notes

- Tested on Termux.
- Python 3.14.
- This repository is intended to improve Android compatibility while preserving the original CLI functionality.

Update

25/9/2026:

- Old version: "0.0.2.dev1+g6c96b1354"
- New version: "0.7.2.post0+android4"
