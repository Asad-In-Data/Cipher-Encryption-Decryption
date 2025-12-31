# Cipher Encryption/Decryption System

<div align="center">

![MIPS Assembly](https://img.shields.io/badge/MIPS-Assembly-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-active-success)

A simple yet effective encryption and decryption system implemented in MIPS Assembly language using the Caesar Cipher algorithm. 

</div>

---

## 📋 Table of Contents

- [About](#about)
- [Features](#features)
- [How It Works](#how-it-works)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
  - [Running the Program](#running-the-program)
  - [Examples](#examples)
- [Technical Details](#technical-details)
- [Project Structure](#project-structure)
- [Documentation](#documentation)
- [Contributing](#contributing)
- [License](#license)
- [Authors](#authors)

---

## 🔍 About

This project implements a **Caesar Cipher** encryption and decryption system in **MIPS Assembly language**. The Caesar Cipher is one of the simplest and most widely known encryption techniques, where each letter in the plaintext is shifted by a fixed number of positions down the alphabet.

This implementation provides an interactive menu-driven interface for:
- Encrypting text messages
- Decrypting encrypted messages
- Preserving non-alphabetic characters (spaces, punctuation, numbers)

---

## ✨ Features

- **Interactive Menu System**: User-friendly command-line interface
- **Caesar Cipher Implementation**: Classic shift cipher algorithm
- **Bidirectional Operation**: Both encryption and decryption supported
- **Case Preservation**: Maintains uppercase and lowercase letters
- **Special Character Handling**: Preserves spaces, punctuation, and numbers
- **Input Validation**: Validates shift key range (1-25)
- **Wrap-Around Logic**: Handles alphabet boundaries correctly
- **Efficient Memory Management**: Optimized buffer usage

---

## 🔧 How It Works

### Caesar Cipher Algorithm

The Caesar Cipher shifts each letter in the plaintext by a fixed number of positions: 

- **Encryption**: `E(x) = (x + k) mod 26`
- **Decryption**: `D(x) = (x - k) mod 26`

Where:
- `x` = position of letter in alphabet (0-25)
- `k` = shift key (1-25)

### Example

**Plaintext**: `HELLO WORLD`  
**Shift Key**: `3`  
**Ciphertext**: `KHOOR ZRUOG`

```
H → K (shift by 3)
E → H (shift by 3)
L → O (shift by 3)
... 
```

---

## 🚀 Getting Started

### Prerequisites

To run this program, you'll need: 

- **MIPS Simulator**:  
  - [MARS (MIPS Assembler and Runtime Simulator)](http://courses.missouristate.edu/KenVollmar/mars/)
  - [SPIM](http://spimsimulator.sourceforge.net/)
  - [QtSpim](http://spimsimulator.sourceforge. net/)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Asad-In-Data/Cipher-Encryption-Decryption. git
   cd Cipher-Encryption-Decryption
   ```

2. **Open in MIPS Simulator**
   - Launch MARS or your preferred MIPS simulator
   - Open the `Project main` file

---

## 💻 Usage

### Running the Program

1. **Load the program** in your MIPS simulator
2. **Assemble** the code (F3 in MARS)
3. **Run** the program (F5 in MARS)

### Main Menu

```
=== Encryption/Decryption System ===
1. Encrypt Message
2. Decrypt Message
3. Exit
Choice: 
```

### Examples

#### Example 1: Encrypting a Message

```
Choice: 1
Enter your message (max 100 chars): Hello World! 
Enter shift key (1-25): 5
Result:  Mjqqt Btwqi! 
```

#### Example 2: Decrypting a Message

```
Choice: 2
Enter your message (max 100 chars): Mjqqt Btwqi!
Enter shift key (1-25): 5
Result: Hello World!
```

#### Example 3: Key Validation

```
Choice: 1
Enter your message (max 100 chars): Secret Message
Enter shift key (1-25): 30
[Returns to menu - invalid key]
```

---

## 🔬 Technical Details

### Memory Organization

```mips
.data
    input_buffer:    .space 101   # Input message buffer
    output_buffer:  . space 101   # Output message buffer
```

### Key Components

1. **Main Program Loop**
   - Menu display and input handling
   - Choice validation and routing

2. **Encrypt Mode**
   - Message input
   - Key input and validation
   - Encryption processing

3. **Decrypt Mode**
   - Message input
   - Key input and validation
   - Decryption processing (negative shift)

4. **Encryption Subroutine**
   - Character-by-character processing
   - Uppercase letter handling (A-Z)
   - Lowercase letter handling (a-z)
   - Non-letter character preservation
   - Wrap-around logic for boundary cases

### Register Usage

| Register | Purpose |
|----------|---------|
| `$s0` | Shift key storage |
| `$s1` | Input buffer pointer |
| `$s2` | Output buffer pointer |
| `$t0` | Current character processing |
| `$v0` | Syscall codes |
| `$a0` | Syscall arguments |

---

## 📁 Project Structure

```
Cipher-Encryption-Decryption/
│
├── Project main              # Main MIPS assembly source code
├── CA report (1).pdf        # Comprehensive project report
├── final slides.pptx        # Project presentation slides
└── README.md                # This file
```

---

## 📚 Documentation

Additional documentation is available: 

- **[CA Report](CA%20report%20(1).pdf)**: Detailed technical report on the implementation
- **[Presentation Slides](final%20slides.pptx)**: Project overview and demonstration

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add some AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### Potential Enhancements

- Implement other cipher algorithms (Vigenère, Substitution)
- Add file I/O capabilities
- Create frequency analysis tools
- Add multi-language support
- Implement cipher breaking algorithms

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## ✍️ Authors

**Asad-In-Data**
- GitHub: [@Asad-In-Data](https://github.com/Asad-In-Data)
- Project Link: [Cipher-Encryption-Decryption](https://github.com/Asad-In-Data/Cipher-Encryption-Decryption)

---

## 🙏 Acknowledgments

- MIPS Assembly language documentation
- Caesar Cipher historical references
- MARS MIPS Simulator team
- Computer Architecture course materials

---

## 📞 Support

If you have any questions or run into issues:

1. Check the [documentation](CA%20report%20(1).pdf)
2. Open an [issue](https://github.com/Asad-In-Data/Cipher-Encryption-Decryption/issues)
3. Contact the maintainer

---

<div align="center">

**⭐ Star this repository if you find it helpful!**

Made with ❤️ using MIPS Assembly

</div>
