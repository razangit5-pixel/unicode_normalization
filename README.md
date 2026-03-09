# 🔤 Unicode Normalization in Python

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=flat&logo=python&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=flat)
![Unicode](https://img.shields.io/badge/Unicode-UTF--8-orange?style=flat)
![Contributions Welcome](https://img.shields.io/badge/Contributions-Welcome-blueviolet?style=flat)

A Python project for understanding and applying **Unicode normalization** — converting text into a consistent, standardized form for reliable processing, comparison, and storage.

---

## 📦 Installation

No external libraries needed — this project uses Python's built-in `unicodedata` module.

**Clone the repository:**
```bash
git clone https://github.com/razangit5-pixel/unicode_normalization.git
cd unicode_normalization
```

**Requirements:**
- Python 3.8+

---

## 🧠 Code Explanation

### What is Unicode Normalization?

Unicode can represent the same character in multiple ways. Normalization ensures they're treated as equal.

**Example — the letter `é`:**
```python
import unicodedata

e1 = '\u00e9'           # é as a single character (precomposed)
e2 = 'e\u0301'          # é as e + combining accent (decomposed)

print(e1 == e2)                          # False ❌ — different bytes
print(unicodedata.normalize('NFC', e1) == unicodedata.normalize('NFC', e2))  # True ✅
```

### Normalization Forms

| Form | Name | What it does |
|------|------|-------------|
| `NFC` | Composed | Combines characters into single form *(most common)* |
| `NFD` | Decomposed | Splits into base + combining characters |
| `NFKC` | Compatibility Composed | Normalizes + replaces compatibility characters |
| `NFKD` | Compatibility Decomposed | Splits + replaces compatibility characters |

### Encoding Example

```python
text = 'I love Python! Shall we book a flight to Jordan?'
encoded = text.encode("utf-8")   # str → bytes
decoded = encoded.decode("utf-8") # bytes → str

print(encoded)   # b'I love Python!...'
print(decoded)   # I love Python!...
```


## 📄 License

This project is licensed under the [MIT License](LICENSE).
