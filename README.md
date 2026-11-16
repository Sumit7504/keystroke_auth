# Keystroke Dynamics Authentication System

A Python-based **behavioral biometric authentication system** that enhances password security by analyzing a user's unique typing rhythm, including key dwell times and inter-key flight times.

Built with Python, Scikit-Learn, NumPy, pynput, and Tkinter.

## Features

- Behavioral authentication using typing patterns.
- Real-time keyboard event capture using `pynput`.
- Dwell time and flight time feature extraction.
- Five-sample user enrollment.
- Random Forest classification with synthetic impostor samples.
- Probability-based authentication (threshold: 0.5).
- Tkinter GUI with separate Login and Register interfaces.

## How It Works

1. **Registration:** User enters a username and password and types it five times.
2. **Feature Extraction:** Captures key dwell times and inter-key flight times.
3. **Model Training:** Generates synthetic impostor samples and trains a user-specific Random Forest classifier.
4. **Model Storage:** Saves the trained model using `joblib`.
5. **Authentication:** Analyzes the user's typing pattern and predicts genuine-user probability.
6. **Access Decision:** Grants access if the predicted probability is at least 0.5.

## Tech Stack

| Technology   | Purpose                                 |
| ------------ | --------------------------------------- |
| Python       | Core development                        |
| Scikit-Learn | Random Forest classification            |
| NumPy        | Feature extraction and noise generation |
| pynput       | Keyboard event capture                  |
| joblib       | Model serialization                     |
| Tkinter      | Desktop GUI                             |

## Project Structure

```text
keystroke-auth/
├── keystroke_auth/
│   ├── gui_auth_app.py
│   └── models/
├── requirements.txt
├── .gitignore
└── README.md
```

## Installation & Usage

**1. Clone the repository**

```bash
git clone https://github.com/<your-username>/keystroke-auth.git
cd keystroke-auth
```

**2. Create a virtual environment and install dependencies**

```bash
python -m venv .venv
```

Windows:

```powershell
.\.venv\Scripts\Activate.ps1
```

Install dependencies:

```bash
pip install -r requirements.txt
```

**3. Run the application**

```bash
python keystroke_auth/gui_auth_app.py
```

**4. Register and Login**

- Register with a username and password.
- Type your password five times to create your typing profile.
- Login by entering your credentials and reproducing your natural typing rhythm.

## Limitations

- Uses only five genuine enrollment samples.
- Synthetic impostor samples may not represent real attackers.
- Repeated characters are not handled correctly.
- Passwords are not securely hashed.
- Model filenames currently expose passwords.
- Intended for educational purposes, not production security.

## Future Improvements

- Support repeated characters and special keys.
- Implement secure password hashing.
- Collect real impostor typing samples.
- Evaluate performance using FAR, FRR, and EER.
- Add automated testing and adaptive user enrollment.

## License

MIT License

## Author

**Sumit Sahu**

[GitHub](https://github.com/Sumit7504) | [LinkedIn](https://linkedin.com/in/sumitsahu7504)
