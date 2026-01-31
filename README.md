<h1 align="center">Regular Expression Parser: High-Performance C Engine</h1>

<p align="center">
  <a href="https://en.cppreference.com/w/c">
    <img src="https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white" alt="C Language">
  </a>
  <a href="https://gcc.gnu.org/">
    <img src="https://img.shields.io/badge/GCC-FFD21E?style=for-the-badge&logo=gnu&logoColor=black" alt="GCC Compiler">
  </a>
  <a href="https://en.wikipedia.org/wiki/Regular_expression">
    <img src="https://img.shields.io/badge/Regex-Logic-blue?style=for-the-badge" alt="Regex Logic">
  </a>
  <a href="https://opensource.org/licenses/MIT">
    <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="MIT License">
  </a>
</p>

<p align="center">
  A robust and modular <b>Regular Expression Parser</b> implemented from the ground up in <b>C</b>. This engine supports a comprehensive suite of meta-characters, including complex quantifiers, character classes, and alternation patterns, enabling high-performance string matching without external libraries.
</p>

<p align="center">
  <a href="#technical-architecture">
    <img src="https://img.shields.io/badge/Architecture-222222?style=flat" />
  </a>
  <span> ° </span>
  <a href="#project-structure">
    <img src="https://img.shields.io/badge/Structure-222222?style=flat" />
  </a>
  <span> ° </span>
  <a href="#regex-logic--features">
    <img src="https://img.shields.io/badge/Features-222222?style=flat" />
  </a>
  <span> ° </span>
  <a href="#technical-specifications">
    <img src="https://img.shields.io/badge/Specs-222222?style=flat" />
  </a>
  <span> ° </span>
  <a href="#deployment--installation">
    <img src="https://img.shields.io/badge/Deploy-222222?style=flat" />
  </a>
</p>

---
<br>

<h2 align="center">Technical Architecture</h2>

The parser is built using a modular, function-driven architecture that processes regex patterns through specialized control modules. Unlike heavy library-based solutions, this engine focuses on precision and low-level memory efficiency:

1.  **Pattern Decomposition:** The system breaks down complex regex patterns into atomic units (literals, meta-characters, or groups).
2.  **Specialized Control Modules:** Implements dedicated matching logic for different regex families:
    *   `squareBracketsControl`: Handles character sets and ranges (`a-z`, `0-9`).
    *   `starControl` & `plusControl`: Manages greedy quantification through iterative expansion.
    *   `dividerControl`: executes alternation logic (`|`) for branch-based matching.
3.  **Recursive Matching Engine:** Orchestrates the results of individual modules to validate whether a candidate string belongs to the language defined by the regex.
4.  **Zero-Dependency Design:** Written purely in standard C, ensuring maximum portability across diverse operating systems and embedded environments.

---
<br>

<h2 align="center">Project Structure</h2>

```
RegexParser/
├── LICENSE                                   # MIT License
├── README.md                                 # Project documentation
├── .vscode/                                  # Development environment config
│
├── Implementation/
│   ├── RegEx_Parser.c                        # Core engine and control modules
│   └── test.c                                # Comprehensive test suite
│
└── Documentation/
    ├── ProjectDocument.pdf                   # In-depth technical methodology
    └── Regex-Template.pdf                    # Syntax reference and use cases
```

---
<br>

<h2 align="center">Regex Logic & Features</h2>

The parser provides a powerful syntax for sophisticated pattern matching across various categories:

### 1. Grouping & Alternation
- **`()` Parentheses**: Encapsulates sub-expressions for priority or grouping.
- **`|` Vertical Bar**: Enables logical "OR" operations (e.g., `gray|grey`).

### 2. Quantifiers
- **`?` Question Mark**: Optional character matching (0 or 1).
- **`*` Asterisk**: Zero or more occurrences.
- **`+` Plus Sign**: One or more occurrences.
- **`{n,m}` Curly Braces**: Precise control over repetition ranges.

### 3. Character Classes & Anchors
- **`[]` Brackets**: Matches any character within the set (supports ranges like `[a-z]`).
- **`^` Caret / `$` Dollar**: Anchors the match to the start or end of the string.
- **`.` Dot**: Matches any character except newlines.
- **`\` Backslash**: Escapes meta-characters for literal matching.

---
<br>

<h2 align="center">Technical Specifications</h2>

<table align="center">
  <tr>
    <th align="center">Component</th>
    <th align="center">Specification</th>
  </tr>
  <tr>
    <td align="center"><b>Programming Language</b></td>
    <td align="center">C (Standard C99/C11)</td>
  </tr>
  <tr>
    <td align="center"><b>Memory Handling</b></td>
    <td align="center">Stateless Buffer-based Processing</td>
  </tr>
  <tr>
    <td align="center"><b>Supported Meta-chars</b></td>
    <td align="center"> ( ) [ ] { } ^ $ . \ | ? * + </td>
  </tr>
  <tr>
    <td align="center"><b>Character Ranges</b></td>
    <td align="center">Alphanumeric, HEX, Special Chars</td>
  </tr>
  <tr>
    <td align="center"><b>Max Group Complexity</b></td>
    <td align="center">Nested Parentheses Support</td>
  </tr>
</table>

---
<br>

<h2 align="center">Deployment & Installation</h2>

### 1. Repository Acquisition
Clone the repository and enter the directory:

```bash
git clone https://github.com/Zer0-Bug/RegexParser.git
```
```bash
cd RegexParser
```

### 2. Compilation
Compile the source code using any standard C compiler (GCC recommended):

```bash
# Compiling the core engine with the test suite
gcc RegEx_Parser.c test.c -o regex_parser
```

### 3. Running the Tests
Launch the compiled executable to verify the parser against predefined patterns:

```bash
./regex_parser
```

---
<br>

<h2 align="center">Contribution</h2>

Contributions are always appreciated. Open-source projects grow through collaboration, and any improvement—whether a bug fix, new feature, documentation update, or suggestion—is valuable.

To contribute, please follow the steps below:

1. Fork the repository.
2. Create a new branch for your change:  
   `git checkout -b feature/your-feature-name`
3. Commit your changes with a clear and descriptive message:  
   `git commit -m "Add: brief description of the change"`
4. Push your branch to your fork:  
   `git push origin feature/your-feature-name`
5. Open a Pull Request describing the changes made.
<br>
All contributions are reviewed before being merged. Please ensure that your changes follow the existing code style and include relevant documentation or tests where applicable.

---
<br>
<h2 align="center">References</h2>

1. **Ken Thompson (1968)** - [Regular Expression Search Algorithm](https://doi.org/10.1145/363347.363387). *Communications of the ACM*.
2. **Jeffrey Friedl (2006)** - [Mastering Regular Expressions](https://www.oreilly.com/library/view/mastering-regular-expressions/0596528124/). *O'Reilly Media*.

---
<br>
<p align="center">
  <a href="mailto:777eerol.exe@gmail.com">
    <img src="https://cdn.simpleicons.org/gmail/D14836" width="40" alt="Email">
  </a>
  <span> × </span>
  <a href="https://www.linkedin.com/in/eerolexe/">
    <img src="https://upload.wikimedia.org/wikipedia/commons/c/ca/LinkedIn_logo_initials.png"
         width="40"
         alt="LinkedIn">
  </a>
</p>

---

<p align="center" style="margin-top:10px; letter-spacing:4px;">
  ∞
</p>
