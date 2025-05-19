########
 Editor
########

This document uses Zed Editor because it’s lightweight and works well
with CLI tools. To configure a language, install the extension and
specify the paths to your LSP and formatter binaries in the project
settings.

#. Install Zed Editor

    .. code:: bash

        scoop install extras/zed

#. Install extensions below via the Extensions tab in Zed

    .. csv-table:: Extensions
        :file: ../_static/enviroment/extensions.csv
        :widths: 3,9
        :align: left

#. Install additional LSPs and formatters using tools

    .. csv-table:: Additional Tools
        :file: ../_static/enviroment/additional_tools.csv
        :widths: 4,2,6
        :align: left

#. Configure project settings to use your tools

.. code:: JSON

    {
        "lsp": {
            "clangd": {
                "binary": {
                    "path": "C:/devtools/llvm/bin/clangd.exe",
                    "arguments": ["--background-index"]
                }
            },
            "lua-language-server": {
                "binary": {
                    "path": "C:/Users/xxx/scoop/apps/lua-language-server/current/bin/lua-language-server.exe"
                }
            },
            "esbonio": {
                "binary": {
                    "path": "python",
                    "arguments": ["-m", "esbonio"]
                }
            }
        },
        "languages": {
            "C++": {
                "formatter": {
                    "external": {
                        "command": "C:/devtools/llvm/bin/clang-format.exe",
                        "arguments": ["--style=microsoft", "{buffer_path}"]
                    }
                },
                "language_servers": ["clangd"]
            },
            "C": {
                "formatter": {
                    "external": {
                        "command": "C:/devtools/llvm/bin/clang-format.exe",
                        "arguments": ["--style=microsoft", "{buffer_path}"]
                    }
                },
                "language_servers": ["clangd"]
            },
            "Lua": {
                "language_servers": ["lua-language-server"]
            },
            "reST": {
                "language_servers": ["esbonio"],
                "formatter": {
                    "external": {
                        "command": "rstfmt"
                    }
                }
            },
            "HTML": {
                "language_servers": ["vscode-html-languageserver"]
            },
            "language_overrides": {
                "JSONC": {
                    "formatter": {
                        "external": {
                            "command": "jq",
                            "arguments": ["--indent", "4", ".", "{buffer_path}"]
                        }
                    }
                }
            }
        }
    }
