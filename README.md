# CISC121-FinalProject

---

## Step 1 - Choose a Problem and an Algorithm

## Chosen Problem
I chose **TA Grading Queue Organizer**


## Chosen Algorithm
**Algorithm:** Merge Sort

### Why Merge Sort fits this problem
1. It sorts efficiently in `O(n log n)` time.
2. It is naturally good for a **step-by-step visual explantion** because it repeatedly:
   - splits the queue into smaller halves
   - compares front items
   - merges them back in order
3. It can be implemented as a **stable sort**, which matters here because the app needs to keep the original arrival order. 

### Assumptions/preconditions
- Each submission must have:
  - valid student ID
  - valid timestamp in the format 'YYYY-MM-DD HH:MM'
  - a file name
- The app does **not** assume the queue is already ordered

### How the app checks/enforces them
- Invalid timestamps are rejected
- Missing fields are rejected
- The file name must end with a common submission extension like .pdf, .zip, .py, .docx, or .txt

### What the user sees during the simulation
The app highlights different parts of the queue:
- **Blue** = left half currently being merged
- **Yellow** = right half currently being merged
- **Red** = current item being compared or placed
- **Green** = segment that has already been merged into sorted order

---

## Step 2 — Plan Using Computational Thinking

### 1. Decomposition:
collect submission records from the user, validate the input fields, store submissions in a queue, run merge sort on the queue using `submitted_at` as the sorting key, record each important step for visualization, display the current step in the GUI, show the final ordered queue

### 2. Pattern Recognition
The repeated pattern in merge sort is: split the queue into smaller halves, keep splitting until each part has one item, compare the first remaining item in each half, place the earlier one into the merged result, continue until the whole segment is merged

### 3. Abstraction
Important: which half is the left half, which half is the right half, which two items are being compared, which item is copied into the merged queue, which part is already sorted
Not important: lower-level Python implementation details, object conversion and serialization, exact internal state-management code used by Gradio

### 4. Algorithm Design
**Input → Process → Output**
- **Input:** student ID, submission time, file name
- **Process:** validate input, store the queue, apply merge sort, record simulation steps
- **Output:** visual queue, step description, final sorted queue


[Final Project.pdf](https://github.com/user-attachments/files/26759322/Final.Project.pdf)

---

## Step 5 - Test and Verify

## Testing
I tested the project with normal inputs and edge cases.

| Test Case | Input | Expected Result | Actual Result |
|---|---|---|---|
| Normal unsorted queue | mixed submission times | queue sorted from earliest to latest | Passed |
| Equal timestamps | multiple students with same time | preserve original arrival order | Passed |
| Empty queue | no submissions | no crash, helpful message | Passed |
| One item | single submission | unchanged queue | Passed |
| Invalid timestamp | wrong date format | validation error shown | Passed |
| Missing file name | blank file field | validation error shown | Passed |

### Edge-case verification
1. Empty queue: The app reports that there is nothing to sort.
2. Single item: merge sort immediately reaches the base case.
3. Equal timestamps: the queue keeps the original arrival order.
4. Bad input: the app rejects invalid timestamps and missing fields.

---

## Steps to Run

### 1. Clone the repository
```bash
git clone <your-github-repo-url>
cd ta-grading-queue-organizer
```

### 2. Create and activate a virtual environment
**macOS / Linux**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

**Windows**
```bash
python -m venv .venv
.venv\Scripts\activate
```

### 3. Install requirements
```bash
pip install -r requirements.txt
```

### 4. Run the app
```bash
python app.py
```

Then open the local Gradio link shown in the terminal.

### 5. Run tests
```bash
python -m unittest discover tests
```

---

## Screenshots
<img width="1440" height="614" alt="Screenshot 2026-04-15 at 4 22 49 PM" src="https://github.com/user-attachments/assets/8de16874-08ca-4019-92b1-85f8462dd6e8" />


---

## Hugging Face Link
https://huggingface.co/spaces/Nina-Busch13/CISC121-FinalProject

---

## GitHub Repository Link
https://github.com/bushybush282/CISC121-FinalProject

---

## Author & AI Acknowledgment
**Author:** Nina Busch

### AI Use
AI was used up to the allowed course level to help with:
- planning the project structure
- refining explanations
- improving code comments and README organization
- generating testing ideas

All code was reviewed, edited, and understood before submission.

