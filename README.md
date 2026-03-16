# CRCODUI

![Version](https://img.shields.io/badge/version-2.0.3-blue.svg)
![Python](https://img.shields.io/badge/python-3.6%2B-green.svg)
![License](https://img.shields.io/badge/license-MIT-purple.svg)

**CRCODUI**
It is a Python library specifically designed to make formatting easier for programmers, shorten code, and perform other tasks such as coloring, input, output, and everything else that attracts clients and distinguishes your work.
هى مكتبة بايثون مصممة خصيصا لتسهيل الديكور على المبرمجين و اختصار الاكواد و غيره من التلوين و الادخال و الاخراج و كل ما يجذب العملاء و يميزك فى عملك



## 🚀 Key Features

* **Installation info:**

Automatically detects and installs missing external packages in the background.
* **Advanced Console Output (`CONSOLS`):** Displays script contents or raw text in the terminal with clean formatting, line numbers, and syntax highlighting.
* **Color Gradients (`COLOR`):** Applies professional color gradient effects to terminal outputs.
* **Code Structuring (`AST`):** Programmatically rebuilds and formats Python files using the Abstract Syntax Tree to ensure clean code.
* **Built-in CLI (`IN_OUT`):** Flexibly handles execution arguments to define input files, outputs, versions, and run modes.
* **Environment Injection (`IMPORT`):** Dynamically injects a wide range of standard libraries and popular tools directly into memory for rapid prototyping.

---

## 📦 Installation

You can install the library and all its dependencies easily via pip:

```bash
pip install CRCODUI

💡 Comprehensive Usage Example
Here is a full example demonstrating how all the components of the library work together seamlessly:
import os
import sys
from CRCODUI import HELP, COLOR, CONSOLE, CONSOLT, AST, IN_OUT, IMPORT

HELP()

print(COLOR("Welcome to CRCODUI Library", " - ", "Powered by @cr_dex"))

IMPORT()

try:
    printt("Rich printt is now injected and available globally!")
except NameError:
    pass

sys_args_backup = sys.argv
sys.argv = ['main.py', 'input_script.py', '-o', 'output_script.py', '-v', '1.0.0', '-m', 'CLI_MODE']

try:
    in_file, out_file, ver, mod = IN_OUT(VERSION="1.0.0")
    print(COLOR("Input: ", str(in_file)))
    print(COLOR("Output: ", str(out_file)))
    print(COLOR("Version: ", str(ver)))
    print(COLOR("Mode: ", str(mod)))
except SystemExit:
    pass

sys.argv = sys_args_backup

code_snippet = "def fetch_data():\n    data = {'status': 200, 'msg': 'Success'}\n    return data\n\nprint(fetch_data())"
CONSOLT(code_snippet)

messy_code = "def   messy_function  ( a ,  b ) : \n return   a+b \n\nprint ( messy_function ( 5 ,  10 ) )"
open("demo_script.py", "w", encoding="utf-8").write(messy_code)

CONSOLE("demo_script.py")

AST("demo_script.py")

CONSOLE("demo_script.py")

if os.path.exists("demo_script.py"):
    os.remove("demo_script.py")

📄 License
This project is licensed under the MIT License. You are free to use, modify, and distribute it.
👨‍💻 Developer
Designed and developed by @cr_dex on Telegram. Feel free to reach out for feedback or contributions.

هل ترغب في أن أكتب لك ملف `setup.py` اللازم لرفع هذه المكتبة إلى PyPI لكي يتمكن أي شخص من تثبيتها باستخدام `pip install CRCODUI`؟

