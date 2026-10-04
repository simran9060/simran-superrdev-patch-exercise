# Assessment Notes

## Summary of Changes

I fixed four high-value issues across the backend, SQL, and frontend:

1. Fixed SQL `AND`/`OR` precedence in `TaskRepository.java` so archived and status filters are applied correctly with title/description search.
2. Removed the artificial `Thread.sleep()` delay from `TaskController.java` to avoid unnecessary API latency and blocked request threads.
3. Fixed the React loading state in `useTasks.js` so loading is cleared when an API request fails.
4. Reset pagination to page 1 when the search query or status filter changes in `App.jsx`.

## What I Chose Not to Change

I did not rewrite the pagination architecture or introduce database-level pagination because the assessment asks for a focused patch. I also did not change the reference Oracle SQL artifact because it is not used by the local application.

## Biggest Remaining Risk

The backend currently loads all matching tasks into memory before applying pagination. For a larger dataset, database-level pagination would be more efficient.

Invalid status, page, and page-size parameters could also use explicit validation instead of relying on runtime behavior.

## Tools / AI Used

I used ChatGPT to help inspect the code, identify potential bugs, explain the root causes, and review the proposed fixes. I tested and reviewed the changes locally, verified the backend and frontend behavior, and made sure I understood each change before committing it.