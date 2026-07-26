The Logic Skeleton — Password Strength Checker

A password strength checker built as Project 1 of the DecodeLabs Industrial Kit (Defensive Logic track, Junior Analyst level). Validates passwords against a defined security policy and classifies them as Weak, Medium, or Strong — using a single linear-time (O(n)) scan.

🔎 Live Demo

Open docs/index.html in any browser, or enable GitHub Pages on this repo (Settings → Pages → deploy from /docs) to get a shareable live link.

📁 What's in this repo
File	Description
password_strength_checker.py	Core CLI implementation in Python
password_strength_checker_gui.py	Tkinter desktop app version
docs/index.html	Browser-based interface ("CIPHERGATE") — HTML/CSS/JS
⚙️ How it works

The checker follows an Input → Process → Output model:

Input — the raw password string
Process — a single pass over every character, flagging uppercase, lowercase, digits, symbols, and Unicode presence
Output — a Weak / Medium / Strong classification

Classification rule:

Length < 8 → Weak (immediate fail)
8+ chars, ≤2 character classes present → Weak
8+ chars, exactly 3 classes present → Medium
8+ chars, all 4 classes present, length ≥ 12 → Strong
Unicode characters present + 3+ classes met → boosted to Strong
🖥️ Running the Python CLI
bash
python password_strength_checker.py
🖼️ Running the Tkinter desktop app

Requires Python 3 with Tkinter (bundled by default on Windows/Mac; on Linux: sudo apt install python3-tk).

bash
python password_strength_checker_gui.py
🌐 Running the web interface

No install needed — just open docs/index.html in any browser.

📊 Why this matters
81% of hacking-related breaches involve weak or stolen passwords
Average breach cost: $4.24M
Automated credential-stuffing accounts for ~25% of enterprise auth traffic

A strength checker catches weak credentials at the earliest possible point — before they're ever stored or used.
