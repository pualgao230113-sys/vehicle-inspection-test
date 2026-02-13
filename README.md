# Take-Home Test: Vehicle Inspection System

A full-stack vehicle inspection management system using React + TypeScript (frontend) and Express + TypeScript (backend).

**Recommended Time: around 1 - 2 hours** — You may take as long as you need, but please don't overthink it.

---

## Backend Tasks (`/backend`)

### Task 1: Implement `createCheck` Controller

**File:** `src/controllers/checkController.ts`

The `POST /checks` endpoint controller is not implemented. You need to:

1. Validate request body using `validateCheckRequest(req.body)`
2. Return 400 with `ErrorResponse` format if validation fails
3. Call `checkService.createCheck()` if validation passes
4. Return 201 with the created check

**Verify:** Remove `.skip` from the test `"should create check and return 201"` in `api.test.ts`

### Task 2: Fix the bug in service function `createCheck`

**File:** `src/services/checkService.ts`

The `hasIssue` flag is not correctly identifying if one inspection record has issue. Find and fix the bug.

**Verify:** Remove `.skip` from the test `"should set hasIssue to true when any item fails"` in `api.test.ts`

Run `npm test` — all tests should pass.

---

## Frontend Tasks (`/frontend`)

### Task 1: Fix Form Input

**File:** `src/CheckForm.tsx`

Check the form to make sure the fields are accepting valid input. You may change the input type where you find it appropriate.

### Task 2: Add Notes Field

**File:** `src/CheckForm.tsx`

Add a textarea for optional notes:

- Maximum 300 characters
- (Optional) Display character counter (e.g., "45/300")
- Include in API request and reset after submission

### Task 3: Implement Toast Notifications

**File:** `src/CheckForm.tsx`

Show visual feedback using the provided `Toast.tsx` and `useToast.ts`:

- Success toast on successful submission
- Error toast on failure
- (Optional) Show good error message in toast on failure

---

## Questions

Please answer these briefly:

1. **Authentication:** If we need to add authentication to this system, how would you approach it?

Authentication: If we need to add authentication to this system, how would you approach it?
I would implement a authentication system such as JWT-based . On the backend, I would add a /login endpoint and a middleware to verify tokens in the Authorization header. On the frontend, I would use an AuthContext to manage the user's logged-in state and protect the inspection form route. However, the current challenge lies in the lifecycle; if the user refreshes the page, the state in memory will be lost.
What I would do in future:
1. draw Sequence Diagram
2. define TypeScript interface
3. Construct AuthContext and handle refresh logic

However, although I learned about and understood the logic in university, I haven't actually done it in practice. Next, I'll look for tutorials online and consult AI tools like Gemini and OpenAI for help.

2. **Improvements:** What other improvements would you implement if this were going to production or if you have more time?

Add Photo Uploads Functionality: Allow users to attach photos of vehicle issues.
Offline Support: Enable drivers to perform checks even in areas with poor signal and synchronize data after reconnecting to the network.
Scalability & High Availability: If the user base grows significantly, I would implement a Message Queue. Instead of writing directly to the main database, the API would push tasks into a queue.
Strategic Batch Processing: For non-urgent data (like routine logs), I would implement Batch Writes at off-peak hours (e.g., 11:00 PM) to reduce database load and operational costs.
Caching Layer: Could cache frequently accessed data like the Vehicle List, so the system doesn't have to query the database every time a user opens the form.

3. **Tech Stack Experience:** Do you have experience with PHP, Vue.js, or mobile app development (React Native/Flutter)?

PHP - Never have any contact with it.
Vue.js - Have a general understanding of it, but haven't actually used it or studied it in depth.
React - Learned JavaScript, but not in depth, and currently learning it online now.
Flutter - Learned about it in uni, but never actually used it to write code.

4. **AI / Tools:** What tools/assistants did you use while working on this assignment (e.g., GitHub Copilot, ChatGPT, etc.)? We appreciate AI usage, we're interested in _how_ you use these tools.

GitHub - Primarily used for storing and retrieving old files in case new files are corrupted or encounter errors.
Gemini - Mainly used to ask questions about code, to find code that I can't remember how to use, and cross-check the syntax for TypeScript interfaces between the frontend and backend.
Visual Studio  - Primarily used for writing code.

5. **Visa Status:** What visa are you currently on?

I am currently working on 485 visa

6. **Languages:** We have users from different backgrounds and industries. What language(s) do you know and what's your proficiency level?

Python - Proficient in coding and programming languages, but not very knowledgeable about Pandas and FastAPI.
C - Wrote many programs in C during uni and have a deep understanding of its logic and code.
HTML - Learned in high school and uni, and covered website architecture and its rules.
Java - Used for group projects during uni, such as designing drone navigation systems, creating card games, etc.
JavaScript - Understand logic and code, but don't have an in-depth understanding of Node.js and Express so far.
MySQL - Know how to filter data, perform calculations and statistics, and to correlate data from different sources.
Haskell - Studied logic and coding in uni (mostly in Declarative language).
Prolog - Studied logic and coding in uni (mostly in Declarative language).
Swift - Used this to develop iOS apps, primarily for front-end tasks and connecting to the Supabase backend.
MATLAB - Frequently use it in calculus and linear algebra to help create 3D graphs and perform calculations.

> **Tip:** You can write your answers directly in this README.md file below each question.

---

## Submission (How to Submit)

1. Create a **public GitHub repository** for this assignment.
2. Push your code with all changes.
3. **Create at least two pull requests (PRs):** one for backend and one for frontend. You may create more (e.g., each task can be an independent PR). You may merge them into the main branch. We can review and may leave comments on your PRs for feedback.
4. Answer questions above.
5. **Please complete and submit within 3 days** unless otherwise discussed.
6. Send the repository link to **admin@enroute-tech.com**.

---

Good luck!
