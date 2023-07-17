# modsys-text-detection
modsys-text-detection (enhanced) - set of automation scripts for various use-cases for detection of toxicity in text

```python
from modsys.client import Modsys
sdk = Modsys()

def evaluate():
    sdk.use("google_perspective:analyze", google_perspective_api_key="#API-KEY")
    return sdk.evaluate(
        [
            {
                "item": "This is hate speech",
                "__expected": {"TOXICITY": {"value": "0.78"}},
                "__trend": "lower",
            },
            {
                "item": "You suck at this game.",
                "__expected": {"TOXICITY": {"value": "0.50"}},
                "__trend": "higher",
            },
        ]
    )

def detectTextApollo():
  sdk.use("google_perspective:analyze", google_perspective_api_key="#API-KEY")
  return sdk.detectText(
    prompt="This is spam",
    community_id="your-app-name-or-username",
    content_id="id-of-content"
  )


if __name__ == "__main__":
    evaluate()
    

```
