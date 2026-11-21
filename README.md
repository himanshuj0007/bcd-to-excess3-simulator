# 🔄 BCD to Excess-3 Converter (NAND-Only Circuit Lab)

An interactive, browser-based digital electronics simulator that demonstrates the conversion of a 4-bit **Binary Coded Decimal (BCD)** input into **Excess-3 (XS-3)** code using **only NAND gates**.

Designed for Digital Electronics practicals and coursework.

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/himanshuj0007/bcd-to-excess3-simulator)

---

## ✨ Features

- **Interactive Inputs:** Toggle individual bits ($A, B, C, D$) or use the quick decimal digit selector ($0–9$).
- **Live Output Display:** Real-time Excess-3 outputs ($W, X, Y, Z$) with LED indicators.
- **NAND-Only Gate Schematic:** Full SVG gate network showing live 0/1 states at each intermediate NAND node and connection.
- **Netlist & Signal Table:** Explicit gate-level interconnects with current signal values.
- **Automatic Truth Table Verification:** Validates outputs for all valid decimal digits ($0–9$) with instant PASS/FAIL checks and don't-care handling for $10–15$.
- **Printable Practical Sheet:** Built-in clean print style for lab documentation and practical record submissions.

---

## 📐 Circuit Design & Boolean Equations

Excess-3 code is formed by adding 3 (`0011` in binary) to the BCD digit:
$$\text{Excess-3} = \text{BCD} + 0011_2$$

Minimized equations using don't-care states ($1010$ to $1111$):
- **$W = A + BC + BD = \text{NAND}(\overline{A}, \overline{BC}, \overline{BD})$**
- **$X = \overline{B}C + \overline{B}D + B\overline{C}\overline{D} = \text{NAND}(\overline{\overline{B}C}, \overline{\overline{B}D}, \overline{B\overline{C}\overline{D}})$**
- **$Y = CD + \overline{C}\overline{D} = \text{NAND}(\overline{CD}, \overline{\overline{C}\overline{D}})$**
- **$Z = \overline{D} = \text{NAND}(D, D)$**

All NOT, AND, and OR operations are implemented strictly with NAND gates.

---

## 🚀 Live Deployment on Render

### Method 1: One-Click Blueprint
Click the button below to deploy instantly using Render Blueprints:

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/himanshuj0007/bcd-to-excess3-simulator)

### Method 2: Manual Setup on Render
1. Go to [Render Dashboard](https://dashboard.render.com).
2. Click **New +** and select **Static Site**.
3. Connect your GitHub repository: `himanshuj0007/bcd-to-excess3-simulator`.
4. Configure settings:
   - **Name:** `bcd-to-excess3-simulator`
   - **Branch:** `main`
   - **Build Command:** *(leave blank)*
   - **Publish Directory:** `.`
5. Click **Create Static Site**.

---

## 💻 Local Usage

Simply open `index.html` in any modern web browser:
```bash
open index.html
```

---

## 📄 License
MIT License

