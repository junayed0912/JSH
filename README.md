JSH: Junayed SHell
JSH is a POSIX-compliant, lightweight command-line interpreter designed for Unix-like operating systems. Built with C++17, it provides a robust interface for process control, file stream redirection, and system navigation across Linux, BSD, and macOS.

Technical Objectives:
The goal of JSH is to provide a clean, dependency-free shell environment that adheres to standard Unix execution patterns while maintaining a modern C++ codebase.

Key Features:
1. POSIX-Standard Execution
JSH utilizes the fundamental Unix process model:

Process Spawning: Uses fork() and execvp() to ensure compatibility with all standard system binaries.

Stream Redirection: Implements dup2() for precise control over stdout (1) and stderr (2), supporting both overwrite (>) and append (>>) modes.

Environment Integration: Dynamically resolves the $PATH and $HOME variables to ensure a seamless transition from other shells.

2. Advanced Lexical Analysis
The JSH tokenizer (handleLine) is designed to handle complex command-line strings:

Literal & Grouping: Full support for single (') and double (") quotes.

Escape Sequences: Sophisticated handling of backslash (\) escape characters to allow special characters in filenames and arguments.

Space Normalization: Automatically handles irregular spacing and leading/trailing whitespace.

3. Native Built-in Suite
Optimized internal functions for core operations:

cd: Directory navigation with ~ home directory resolution.

pwd: Current directory reporting via getcwd.

type: Command origin diagnostics (built-in vs. external).

echo: Formatted output with full quote/escape support.

help: Integrated command documentation.

🛠️ Build & Requirements
JSH is designed to be highly portable across any POSIX-compliant system.

Compiler: g++ or clang++ (C++17 support required).

OS: Linux (Fedora/Ubuntu/etc.), FreeBSD, or macOS.

./jsh
🗺️ Roadmap
[ ] Tab Autocompletion: (Planned) Implementing readline or custom TTY handling for command and path completion.

[ ] Piping: Connecting processes via pipe() for complex command chains.

[ ] Job Control: Background process management (&).

[ ] Scripting Support: Ability to execute .jsh scripts.
