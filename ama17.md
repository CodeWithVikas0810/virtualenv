# AMA Session Questions and Answers

**Adhikya Edammala - What is an MCP Server?**
MCP stands for **Model Context Protocol**. An MCP Server is a server that acts as a **bridge between an AI model and external tools, applications**. It allows the AI to access information or perform actions that are not available inside the AI model itself.

---

**Allanki VV Manikanta Sai - Give some examples of MCP Servers.**
Some common examples of MCP Servers include:

1. **File System MCP Server** – Allows an AI to read, create, or manage files.

2. **Database MCP Server** – Allows an AI to interact with databases.

3. **GitHub MCP Server** – Allows AI to work with GitHub repositories.

4. **Browser/Web MCP Server** – Allows an AI to access web information.

5. **Slack MCP Server** – Allows AI to interact with Slack.

---

**Boorle Sowmya Sri Lakshmi - Name some vulnerabilities an application can have.**
Application vulnerabilities are **security weaknesses or flaws** that attackers can exploit to access data, modify information, or perform unauthorized actions.

Some common vulnerabilities are:

1. **SQL Injection** – An attacker inserts malicious SQL commands into an application.

2. **Cross-Site Scripting (XSS)** – An attacker injects malicious JavaScript into a webpage.

3. **Broken Authentication** – Weak login or session management allows attackers to access another user's account.

4. **Broken Access Control** – A user can access resources or functions they are not authorized to use.

5. **Insecure File Upload** – An application allows users to upload dangerous files without proper validation.

6. **Security Misconfiguration** – Incorrect security settings expose an application to attacks.

---

**Md Musharaf - What is RAG?**
RAG stands for **Retrieval-Augmented Generation**. It is a technique that allows an AI model to **retrieve relevant information from an external knowledge source before generating an answer**.

Normally, an AI model answers based on the information it learned during training. With RAG, the system first searches a knowledge base, retrieves relevant information, and then provides that information to the AI model to generate a better answer.

---

**Nayunipatruni Harsha Vardhan - What are tools?**
Tools are **external functions or capabilities that an AI agent can use to perform tasks**. An AI model can understand and reason about a task, but tools allow it to actually interact with external systems.

Examples of tools include:

* **Calculator tool** – performs mathematical calculations.
* **Web search tool** – searches for current information.
* **Database tool** – retrieves or updates database information.
* **File tool** – reads or writes files.
* **API tool** – communicates with external applications.

---

**Rongala Vasu - What is a sub-agent?**
A **sub-agent** is a specialized AI agent that works under the control or coordination of a **main/parent agent**. It is usually given a specific task and then sends its result back to the main agent.

Sub-agents are useful when a task is complex and can be divided into multiple smaller tasks.

**Example:**
Suppose a user asks:

*"Research AI trends, compare the top technologies, and prepare a report."*

A main AI agent can divide the task among different sub-agents:

* **Research sub-agent** → collects information about AI trends.
* **Comparison sub-agent** → compares different technologies.
* **Writing sub-agent** → prepares the final report.

The main agent then **combines the results from all the sub-agents** and gives the final response to the user.
