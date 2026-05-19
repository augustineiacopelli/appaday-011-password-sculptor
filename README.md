# 011 · Password Sculptor

A cryptographically strong password generator with live entropy-based strength scoring and full character set control. Built for Day 11 of AppADay.

**Live app:** https://augustineiacopelli.github.io/appaday-011-password-sculptor

## What It Does

Password Sculptor generates secure passwords using the browser's Web Crypto API (`crypto.getRandomValues`). You control length (8–64 characters), which character sets to include (uppercase, lowercase, numbers, symbols), and whether to exclude visually ambiguous characters (0, O, l, I, 1). A live strength meter calculates Shannon entropy in bits and labels the result from Very Weak through Fortress.

## How to Use

1. Adjust the length slider and toggle character sets to your requirements.
2. Optionally enable **Exclude Ambiguous** to remove characters that look alike.
3. Click **Generate Password** or the refresh icon to sculpt a new password.
4. Click the copy icon, the password display, or the copy button to copy to clipboard.

## Technical Notes

- All randomness comes from `crypto.getRandomValues()` — never `Math.random()`.
- Generation guarantees at least one character from each active character set before filling randomly, preventing accidental omissions.
- Strength is calculated as `length × log₂(charsetSize)` entropy bits, not pattern-matching heuristics.
- No network requests. No data leaves the device. No dependencies or frameworks.

## Definition of Complete

- [x] Generates passwords using Web Crypto API
- [x] Length control: 8–64 characters via slider
- [x] Four toggleable character sets with guaranteed representation
- [x] Exclude ambiguous characters option
- [x] Live entropy-based strength meter with bit count
- [x] One-click copy with visual confirmation
- [x] Mobile-friendly at 375px viewport
- [x] Published to GitHub Pages
