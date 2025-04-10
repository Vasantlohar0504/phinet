# PHINet
Custom phishing detection boosting model using handcrafted features and a lightweight decision tree ensemble.

---

## Example Usage

```python
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
