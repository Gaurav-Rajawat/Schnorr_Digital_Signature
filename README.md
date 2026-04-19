# 🔐 Schnorr Signature Scheme Implementation

This project demonstrates the implementation of the **Schnorr Digital Signature Scheme**, a cryptographic algorithm used for secure authentication, data integrity, and non-repudiation.

---

## 📌 Overview

The Schnorr Signature Scheme is a **public-key cryptographic algorithm** based on the difficulty of the **Discrete Logarithm Problem (DLP)**. It is widely used in modern cryptographic systems and blockchain technologies due to its simplicity, efficiency, and strong security properties.

---

## ⚙️ Features

* ✔️ Safe prime generation (`p = 2q + 1`)
* ✔️ Generator selection (`g`)
* ✔️ Key generation (private & public keys)
* ✔️ Message signing
* ✔️ Signature verification
* ✔️ SHA-256 based hash function
* ✔️ Interactive UI using Jupyter Widgets
* ✔️ Execution time measurement (KeyGen → Verify)

---

## 🧠 Algorithm Workflow

### 1. Parameter Generation

* Generate a large prime `q`
* Compute safe prime `p = 2q + 1`
* Select generator `g`

### 2. Key Generation

* Private key: `x`
* Public key: `y = g^x mod p`

### 3. Signing

* Choose random `k`
* Compute commitment: `r = g^k mod p`
* Compute challenge: `e = H(r, m)`
* Compute response: `s = (k + x·e) mod (p-1)`

### 4. Verification

* Verify:
  g^s ≡ r · y^e (mod p)

---

## 🧪 Example Output

```
Public Key (y): 89902

Signature:
r = 81285
s = 50822

Result: ✅ Signature is VALID
Execution Time: 0.000123 sec
```

---

## 🛠️ Technologies Used

* Python 🐍
* hashlib (SHA-256)
* random module
* SageMath functions (for prime generation & modular arithmetic)
* Jupyter Notebook
* ipywidgets (for UI)

---

## 📂 Project Structure

```
📁 schnorr-signature/
│── schnorr.ipynb       # Main implementation
│── README.md           # Project documentation
```

---

## 🚀 How to Run

### 1. Clone the repository

```
git clone https://github.com/your-username/schnorr-signature.git
cd schnorr-signature
```

### 2. Open Jupyter Notebook

```
jupyter notebook
```

### 3. Run the notebook

* Execute all cells
* Enter a message
* Generate and verify signature

---

## ⚠️ Security Note

This implementation is for **educational purposes only**:

* Uses small prime sizes (not secure for real-world use)
* Random values are not cryptographically secure
* Private key (`x`) and nonce (`k`) are exposed in demo

---

## 📈 Future Improvements

* Use large primes (1024+ bits)
* Replace random with secure RNG
* Implement elliptic curve Schnorr (used in blockchain)
* Add attack demonstration (nonce reuse)
* Optimize performance

---

## 📚 Applications

* Blockchain (e.g., Bitcoin Taproot)
* Digital signatures
* Secure communication
* Authentication systems

---

## 👨‍💻 Author

Gaurav Singh

---

## 📜 License

This project is open-source and available under the MIT License.
