# Build and Call Your Own MCP Tool
Name: Bhanu Avusherla

## 1. How many tools were listed, and what changed in the client?

The original server had 8 tools. After adding predict_both,
my client listed 9 tools.

No client-side registration was needed to make the tool appear.
The client discovered it through server.list_tools().
The client then called predict_both by name to use it.

## 2. On how many patients did the models disagree?
## Which model was correct for each patient?

The models disagreed on 8 of the 114 test patients.

| Patient | True class | Logistic regression | KNN | Correct model |
|---|---|---|---|---|
| 3 | benign | benign | malignant | Logistic regression |
| 25 | benign | benign | malignant | Logistic regression |
| 48 | benign | benign | malignant | Logistic regression |
| 53 | malignant | benign | malignant | KNN |
| 76 | malignant | malignant | benign | Logistic regression |
| 80 | benign | benign | malignant | Logistic regression |
| 99 | benign | benign | malignant | Logistic regression |
| 102 | malignant | malignant | benign | Logistic regression |

## 3. Which model was right more often when they disagreed?

Logistic regression was correct in 7 of the 8 disagreement cases.
KNN was correct in 1 case.

Therefore, logistic regression was right more often when
the models disagreed.

## 4. Why does the triple-quoted description matter?

The description explains what the tool does. An AI app can
read it to decide whether the tool is useful for a user's
request and when to call it. A clear description helps the
AI choose the appropriate tool.

## 5. Why is logging every tool call useful?

Logging creates a record of which tool was called, its
request ID, and whether the call succeeded or failed.
This helps developers investigate errors and trace what
happened during a run.

I checked the audit log and confirmed that my predict_both
calls were recorded with success status.

![alt text][def]

[def]: image.png
