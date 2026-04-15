# CISC121-FinalProject

---

## Chosen Problem
I chose **(1) TA Grading Queue Organizer**.

The app stores a list of submissions in the form:
- student_id
- submitted_at
- file_name

The user can add new submissions, load demo data, and step through the process of reordering the queue so that all submissions are arranged in fair submission-time order.

---

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
