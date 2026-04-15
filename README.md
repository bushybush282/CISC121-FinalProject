# CISC121-FinalProject

---

## Step 1 — Choose a Problem and an Algorithm

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

