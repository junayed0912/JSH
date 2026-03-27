💻 JSH: Junayed SHell
A POSIX-compliant, lightweight command-line interpreter for Unix-like systems.

JSH is built with C++17 to provide a robust interface for process control, file stream redirection, and system navigation across Linux (Fedora/Ubuntu), BSD, and macOS.

🚀 Key Features
1. POSIX-Standard Execution
  JSH adheres to standard Unix execution patterns:

  Process Spawning: Uses fork() and execvp() for compatibility with all system binaries.

  Stream Redirection: Implements dup2() for precise control over stdout (1) and stderr (2). Supports:

        Overwrite (>)

        Append (>>)

  Environment Integration: Dynamically resolves $PATH and $HOME for seamless transitions.



2. Advanced Lexical Analysis

   The custom handleLine tokenizer manages complex strings:

        Quotes: Full support for single (') and double (") quotes.

        Escaping: Handles backslash (\) escape characters for filenames and arguments.

        Normalization: Automatically cleans up irregular spacing and whitespace.



4. Native Built-in Suite
   Optimized internal functions for zero-latency operations:

        cd — Directory navigation with ~ resolution.

        pwd — Real-time reporting via getcwd.

        type — Identifies if a command is builtin or external.

        echo — Formatted output with full quote/escape support.

        help — Integrated command documentation.

        clear — Terminal screen reset.

5.Build & Installation

To run this project on your machine, follow these steps:

  Install Make (if not already installed):

        On Fedora: sudo dnf install make

        On Ubuntu/Debian: sudo apt install make

        On macOS: xcode-select --install

  Compile the source:

        make
        
  Execute the shell:

        ./main
   

🗺️ Roadmap

        [ ] Tab Autocompletion: Custom TTY handling for command/path completion.

        [ ] Piping: Connecting processes via pipe().

        [ ] Job Control: Background process management (&).

        [ ] Scripting: Support for executing .jsh scripts.
