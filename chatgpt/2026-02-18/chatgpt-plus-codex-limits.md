# ChatGPT Plus Codex Limits

> **Platform:** CHATGPT | **Date:** 18/02/2026, 13:29:02 | **Turns:** 2
> **Source:** [Open Original](https://chatgpt.com/c/69957133-fa44-8323-81e7-e2294b1165e0)

---

## USER

what are chatgtp plus codex limits

---

## ASSISTANT

Here’s a clear summary of what **ChatGPT Plus** and **Codex (inside ChatGPT)** limits look like in practice as of early 2026 — including what you can expect and the common restrictions users run into:

🔹 **ChatGPT Plus (General Usage Limits)**
ChatGPT Plus gives you much **higher usage allowances** than the free plan, but it is *not unlimited*.
**Typical limits for ChatGPT Plus:**

- You can send *many more messages* than free users before hitting a cap (often measured per time window like 3–5 hours).

- You get access to better models like **GPT-5.2 / GPT-5 variants** and tools like *Code*, *Uploads*, and *Deep Research* (but those also have quotas). [Northflank](https://northflank.com/blog/chatgpt-usage-limits-free-plus-enterprise?utm_source=chatgpt.com)

- Limits often reset on fixed schedules (every few hours). [Northflank](https://northflank.com/blog/chatgpt-usage-limits-free-plus-enterprise?utm_source=chatgpt.com)


💡 *Example (reported community figures, approximate):*
ChatGPT Plus might allow something like **~160 GPT-5 messages every 3 hours** before it throttles or switches to simpler models. [Northflank](https://northflank.com/blog/chatgpt-usage-limits-free-plus-enterprise?utm_source=chatgpt.com)
Exact limits aren’t officially documented in a single published OpenAI doc — and they can change based on load.

🔹 **Codex (Coding Assistant Inside ChatGPT Plus)**
Codex (the *coding agent* included with ChatGPT Plus) also has usage limits — separate from general chat limits — and they work like a **quota you can burn through**:
🧠 What Codex Does

- Helps with code generation, codebase refactoring, CI tasks, testing workflows, pull-request suggestions, etc. [OpenAI](https://openai.com/index/introducing-codex/?utm_source=chatgpt.com)


⏱ Common Codex Usage Restrictions

- **Codex usage is limited based on your plan.**
ChatGPT Plus users get noticeably **lower quotas** than Pro or higher tiers. [apidog](https://apidog.com/blog/codex-usage-limits/?utm_source=chatgpt.com)

- Limits are often expressed as **messages/tasks per time window** (e.g., per 5 hours) and **weekly quotas**. [apidog](https://apidog.com/blog/codex-usage-limits/?utm_source=chatgpt.com)

- When the limit is hit, Codex will stop accepting new tasks until the reset period. [apidog](https://apidog.com/blog/codex-usage-limits/?utm_source=chatgpt.com)


📊 Approximate Codex Limits (Plus Tier)
*These are reported ranges, not official fixed numbers*:
Limit TypeTypical Plus Tier QuotaMessages or coding tasks per 5 hours~30–150Heavy Cloud / workspace tasks per 5h~10–60Weekly coding tasks~10–25*(Actual numbers vary by activity complexity & OpenAI load)* [apidog](https://apidog.com/blog/codex-usage-limits/?utm_source=chatgpt.com)
⚠️ Some users report hitting their limits **very quickly** — sometimes even after just a few large requests — due to how Plus quotas are enforced, especially in tools like Codex CLI or VS Code extensions. [GitHub](https://github.com/openai/codex/issues/2448?utm_source=chatgpt.com)

🧩 Other Clarifications
🔸 Context / Token Limits

- ChatGPT Plus web use historically had limits like **~32k tokens** for context in chats. GPT-5 models can support far larger windows internally (same system as Codex). [GitHub](https://github.com/openai/codex/discussions/1999?utm_source=chatgpt.com)


🔸 Reset and Quota Behavior

- Both chat and Codex quotas tend to reset on **fixed windows** (e.g., every 5 h or weekly), and hitting one quota can block further use until reset. [apidog](https://apidog.com/blog/codex-usage-limits/?utm_source=chatgpt.com)


🔸 Purchasing Extras

- If you exhaust your plan’s quota, OpenAI allows **buying additional credits** to continue using Codex without upgrading plans. [OpenAI Developers](https://developers.openai.com/codex/pricing/?utm_source=chatgpt.com)



🧠 Bottom Line
**ChatGPT Plus enhances capabilities but still has limits:**

- More messages per time window vs free.

- Better model performance and tools.

- Usage quotas apply (messages, tasks, and tool-specific quotas).

- Codex usage is subject to its own quotas inside your Plus plan that can be restrictive for heavy development work.


**For truly “unlimited” coding/editor AI usage**, many developers choose **Pro or higher** plans, or use **Codex via API token billing**, which is metered rather than quota-capped.

If you want, I can compare these limits with **ChatGPT Pro** (heavily higher quotas) or explain how you can


---
*Archived by [StoreChat](https://github.com/Adi-gitX/StoreChat) on 2026-02-18*
