# PHINet
Custom phishing detection boosting model using handcrafted features and a lightweight decision tree ensemble.

---

##  Featured Project: PHINet

PHINet is a custom-built Python package that detects phishing emails using handcrafted features and a lightweight boosting model.

🔐 Features:
- Detects phishing based on email content, URLs, attachments, and sender domain
- Uses a custom boosting algorithm (PHINetBoost)
- Easy to install and extend

📦 Available on [PyPI](https://pypi.org/project/phinet)  
📁 Source code: [GitHub Repo](https://github.com/Vasantlohar0504/phinet)

---

## 📦 Installation

```bash
pip install phinet



# PHINet
Custom phishing detection boosting model using handcrafted features and a lightweight decision tree ensemble.

---

from phinet.model import PHINetBoost, PHINetFeatureEngine
import pandas as pd

# Sample email input
df = pd.DataFrame([{
    'email_id': 'scammer@fakebank.com',
    'email_body': 'Urgent: Verify your account or it will be suspended!',
    'urls': 'http://fakebank-login.com',
    'attachments': 'dangerous.zip'
}])

# Extract features and run prediction
engine = PHINetFeatureEngine()
X = engine.transform(df)

model = PHINetBoost(n_estimators=5, max_depth=3)
model.fit(X, [1])  # 1 means 'Phishing' for demo
print("Prediction:", "Phishing" if model.predict(X)[0] == 1 else "Legitimate")



---
