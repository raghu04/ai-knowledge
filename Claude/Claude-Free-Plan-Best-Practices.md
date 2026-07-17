If you're on the **Claude Free plan**, you can get much better continuity by treating each 5-hour window as a "work session." Here are the practices that work best.

### 1. Always keep the same chat

Don't start a new conversation after the limit resets.

✅ Good:

> Open the same chat → "Continue from where you stopped."

❌ Avoid:

> Starting a brand-new chat and asking the same question again.

---

### 2. Use "Continue" instead of "Retry"

If the answer was cut off:

```
Continue from the last completed paragraph.
```

or

```
Continue exactly where you stopped. Don't repeat previous content.
```

This usually produces a smoother continuation than Retry.

---

### 3. Tell Claude not to repeat itself

A good continuation prompt is:

```
Continue exactly where you left off.
Do not repeat earlier sections.
Start from the next unfinished part.
```

This reduces duplicate text.

---

### 4. If it's coding, specify where to continue

Instead of:

> Continue

Use:

```
Continue implementing from the UserService class.
Do not rewrite completed files.
Only generate the remaining code.
```

or

```
Continue from Step 7.
```

This saves messages.

---

### 5. Before you're close to the limit, ask for a checkpoint

If you're working on something large, ask:

```
Before continuing, summarize our progress in 10 bullet points.
```

or

```
Create a checkpoint of everything completed so far.
```

If the limit hits later, you have a compact reference.

---

### 6. Break huge tasks into milestones

Instead of:

> Build an entire SaaS application.

Do:

```
Part 1: Database schema

Part 2: Backend APIs

Part 3: Authentication

Part 4: Frontend

Part 5: Deployment
```

If the limit hits after Part 2, you only resume from Part 3.

---

### 7. Ask Claude to number its sections

Example:

```
Produce 20 sections.
Number them 1–20.
```

If it stops at Section 12:

```
Continue from Section 13.
```

Much easier than finding the stopping point yourself.

---

### 8. For code, ask it to list remaining work

Before the limit, ask:

```
List all remaining tasks before continuing.
```

Example:

```
✓ Authentication
✓ Database
✓ Models
□ APIs
□ Tests
□ Docker
□ Documentation
```

After the reset:

```
Continue with APIs.
```

---

### 9. Save important outputs locally

Copy important code, plans, or summaries into a local file (or notes). If something goes wrong, you won't lose progress or spend messages reconstructing it.

---

### 10. If Claude forgets context, remind it briefly

Don't paste the entire conversation again.

Instead:

```
We already completed:
- Authentication
- User CRUD
- JWT middleware

Next task:
Implement Product APIs.
```

A short recap is often enough.

---

## A prompt template you can reuse after the limit resets

```text
Continue exactly where you left off.

Do not repeat previous content.
Use the existing context from this chat.
Resume from the next unfinished section.
If you're writing code, only generate the remaining code.
```

## For very large projects (my favorite workflow)

1. Work until you're near the limit.
2. Ask Claude:

   ```
   Summarize everything completed.
   List remaining tasks.
   Indicate the exact next step.
   ```

3. Copy that summary into your notes.
4. After the 5-hour reset, open the same chat and say:

   ```
   Continue from the next step in the checkpoint.
   ```

This approach minimizes wasted messages and makes it much easier to resume long coding sessions on the Free plan.
