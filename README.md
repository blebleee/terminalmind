# terminalmind

<p align="center">
  <img src="assets/logo.png" alt="terminalmind logo" width="400"/>
</p>

**Current Version: v1.0.1**

### What's New in v1.0.1

- **New Feature**: Integration with `llama.cpp` framework, enhancing the tool's capabilities.
- **Bug Fixed**: Remove prompt input for better user experiments
- **Documentation Updates**: Release notes added along with updated instructions for working with llama.cpp

For more detailed information, please see the [release notes](https://github.com/namtranase/terminalmind/releases/tag/v1.0.0).

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)

`terminalmind`, now accessible via the `temi` command, is a command-line tool designed to enhance coding efficiency by suggesting relevant code snippets and facilitating text and PDF data processing directly in the terminal. This approach promotes a seamless development workflow, keeping developers focused within their coding environment.

## Acknowledgments

`terminalmind` builds on the work of the [llama.cpp](https://github.com/ggerganov/llama.cpp) project. Special thanks to [Georgi Gerganov](https://github.com/ggerganov) and contributors for their groundbreaking work in creating a C++ interface for the LLM model. We encourage `terminalmind` users and developers to support and contribute to `llama.cpp`.

## Supported Features

Demo:
<p align="center">
  <img src="assets/examples.png" alt="Examples"/>
</p>

- [x] **Q&A in Terminal**: Interactive question-and-answer functionality directly in your command line.
- [x] **PDF Information Retrieval**: Extract and analyze information from both local and web-based PDF files based on keyword.
- [x] **Online Article Summarization**: Quickly summarize the content of online articles with a simple command.
- [x] **temi integrates the llama.cpp framework**: `temi` now supports multiple models provided by the llama.cpp framework, enhancing its functionality.
- [ ] **Command Execution Based on User Input**: *Upcoming feature* to execute relevant terminal commands automatically based on user queries.
- [ ] **GPU Acceleration for Enhanced Performance**: *In development* – leveraging GPU acceleration for faster response times and improved efficiency.
- [ ] **Integration with llama.cpp Server**: Enhance response times and model management by interfacing with llama.cpp's dedicated server.
- [ ] **Interactive App and Web Launcher**:  Execute applications and navigate to websites directly through keyword-triggered commands.
- [ ] **Docker Compatibility**: Run temi seamlessly in Docker containers for isolated and consistent development environments.
- [ ] **User-Friendly Settings Interface**: Customize temi with ease using a graphical settings panel.

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#description">Description</a></li>
    <li><a href="#installation">Installation</a></li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
  </ol>
</details>

## Description

`terminalmind`, accessible via the `temi` command, offers functionalities like text summarization, content retrieval from PDFs, and more, using an integrated language model. Designed for terminal use, it caters to developers, researchers, and technology enthusiasts.

## Installation

Clone the repository:
```bash
git clone https://github.com/namtranase/terminalmind.git
cd terminalmind
```

Install requirement packages:
```bash
sudo apt install python3-requests python3-bs4 python3-pypdf2
```

Download the model:
```bash
./scripts/download_model.sh
```

Install the package by scripts:
```
./scripts/install_temi.sh
```

Or build step by step.

Build the Debian package:
```bash
dpkg-deb --build temi-packaging temi.deb
```

Install package using `dpkg`:
```bash
sudo dpkg -i temi.deb
```

## Usage

After installation, you can use temi but first, it needs to update the model file. Start temi for the first time and paste the absolute path to the model downloaded above. For example:
```bash
temi Hello
# Model file not found at /llm_models/model.gguf.
# Please enter the absolute path to your .gguf model file:
models/model.gguf
```

And now you can use `temi` as the terminal assistant:
```bash
temi how to make a python package
#  To create a Python package, follow these steps:

# 1. Choose a name for your package and ensure it's unique.
# 2. Create a new directory with that name.
# 3. Inside the directory, create a file named `__init__.py` to mark the directory as a Python package.
# 4. Write your Python code in subdirectories or files inside the package directory.
# 5. Install any required dependencies in a `requirements.txt` file or `setup.py`.
# 6. To distribute, use tools like setuptools, Twine and PyPI to create a distribution package.%

```
## Contributing

Contributions to `temi` are greatly appreciated, whether they involve submitting pull requests, reporting bugs, or suggesting enhancements.

### Getting Started
For detailed instructions on working with the llama.cpp submodule, including setup and usage, refer to the WORK_WITH_LLAMACPP.md file.

1. Install repo and submoudles:
```bash
git clone --recurse-submodules https://github.com/namtranase/terminalmind.git
```

2. Install Development Dependencies:
```bash
pip install -r requirements/dev_requirements.txt
```

3. Set Up Pre-Commit Hooks:
```bash
pre-commit install
```

### Making Contributions

- Fork and Clone the Repository: Start by forking the repository and then clone your fork to your local machine.

- Create a New Branch: Work on your changes in a new git branch. This helps to keep your modifications organized and separate from the main codebase.

- Submit a Pull Request: Once your changes are complete, push them to your fork and submit a pull request to the main terminalmind repository.

## License

`terminalmind` is MIT licensed, as found in the [LICENSE](https://github.com/namtranase/terminalmind/LICENSE) file.
