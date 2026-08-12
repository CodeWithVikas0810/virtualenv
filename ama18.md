# AMA Session Questions and Answers

### 1. Adhikya Edammala — What is Red Teaming?

**Red teaming** is the practice of testing a system, application, or organization by acting like an attacker. The goal is to find security weaknesses before real attackers can exploit them. In cybersecurity and AI, red teams may try techniques such as prompt injection, data leakage, unauthorized access, or other attacks.

### 2. Allanki VV Manikanta Sai — What is RAG?

**RAG (Retrieval-Augmented Generation)** is a technique where an LLM retrieves relevant information from an external knowledge source and then uses that information to generate an answer. It helps provide more accurate, up-to-date, and context-specific responses without retraining the model.

**Example:** A chatbot can search a company's documents and use the retrieved information to answer employee questions.

### 3. Boorle Sowmya Sri Lakshmi — How does routing help in React?

**Routing** in React allows an application to display different components or pages based on the URL without completely reloading the webpage. Libraries such as **React Router** are commonly used for this.

**Example:**

* `/home` → Home component
* `/about` → About component
* `/products` → Products component

This helps build **single-page applications (SPAs)** with multiple views.

### 4. Md Musharaf — What is the difference between an LLM and an Agent?

| LLM                                                 | Agent                                                                       |
| --------------------------------------------------- | --------------------------------------------------------------------------- |
| Generates text or responses based on input.         | Uses an LLM to perform tasks and make decisions.                            |
| Usually responds to a prompt.                       | Can plan, use tools, and take actions.                                      |
| Doesn't necessarily interact with external systems. | Can interact with APIs, databases, browsers, or other tools.                |
| Example: ChatGPT answering a question.              | An AI system that searches the web, analyzes results, and completes a task. |

**In simple terms:** An **LLM generates**, while an **Agent uses an LLM to reason, act, and accomplish a goal**.

### 5. Nayunipatruni Harsha Vardhan — What is `useContext`?

`useContext` is a **React Hook** used to access shared data from a Context without passing props through every component.

It is useful for sharing data such as:

* User information
* Theme settings
* Language preferences
* Authentication state

**Example:**

```jsx
const user = useContext(UserContext);
```

This allows a component to directly access the value provided by `UserContext`.

### 6. Rongala Vasu — What is the difference between Vertical and Horizontal Scaling?

| Vertical Scaling                           | Horizontal Scaling                                         |
| ------------------------------------------ | ---------------------------------------------------------- |
| Increases the power of an existing server. | Adds more servers to the system.                           |
| Example: More CPU, RAM, or storage.        | Example: Adding multiple application servers.              |
| Usually simpler to implement.              | Requires load balancing and distributed-system management. |
| Has a hardware limit.                      | Can scale by adding more machines.                         |
