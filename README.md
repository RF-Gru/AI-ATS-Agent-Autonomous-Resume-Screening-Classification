# AI-ATS-Agent-Autonomous-Resume-Screening-Classification

🎯 1. Project Summary: Automation Meets Precision

This project delivers a fully autonomous AI agent designed to revolutionize the initial candidate screening process. By integrating modern LLM development practices with a powerful workflow automation tool, this solution tackles the high volume and inconsistency inherent in manual resume review.

Problem Solved: Automating the slow, bias-prone process of comparing a job description (JD) against a candidate's resume.

Core Achievement: Created a high-accuracy, end-to-end automation pipeline that delivers a structured, objective hiring recommendation in under 8 seconds per candidate.

Skills Demonstrated: AI Agent Design, Prompt Engineering, Structured LLM Output (Pydantic), Workflow Orchestration (n8n), Python Development, and Performance Metrics.

<img width="1117" height="434" alt="Screenshot 2025-12-02 at 18 54 18" src="https://github.com/user-attachments/assets/a30eb5db-58d0-48f9-9c05-0e4ee493c9b4" />


🚀 2. The Narrative: From Inbox to Interview

In a fast-growing company, recruiters can spend up to 70% of their time on initial screening—a bottleneck that delays hiring and leads to burnout.

Our Solution: The ATS Agent transforms this process. When a candidate applies, the agent reads both the resume and the job description, analyzes the core requirements, and immediately generates a structured, quantitative assessment of the fit. This assessment then automatically triggers the next step—sending an acceptance email, a polite rejection, or flagging for human review—freeing up the recruiting team to focus only on qualified candidates.

🛠️ 3. Technical Architecture & Tools

The agent's strength lies in its ability to separate complex AI logic (Python/LangChain) from scalable workflow management (n8n).

a. The Agent's Flow (Orchestration with n8n)

The entire pipeline is built and managed using n8n, a low-code workflow automation tool. This orchestration layer handles the non-AI tasks: listening for new applications, routing the data to the AI component, and executing the final action (sending an email).

The key steps in the automated workflow are:

Form Trigger: A new resume and JD are received.

PDF Parsing: The resume is converted into machine-readable text.

AI Agent Call: The text and JD are sent to the Python Agent.

Decision Gate: The Agent's structured output determines the next step: Accepted leads to an interview scheduling email; Rejected sends a polite notification.

b. The Intelligence Core (Python & LangChain)

The core intelligence is a Python service leveraging the LangChain framework. This framework manages the chain of actions required to produce a reliable result:

Data Ingestion: The agent processes the raw text of the resume and JD.

Prompt Engineering: A highly refined prompt directs the LLM (e.g., OpenAI/Gemini) to act as a seasoned hiring manager, focusing its analysis on only the most critical skills.

Structured Output (Pydantic): The agent is forced to return its complex analysis in a predictable, reliable JSON format using a Pydantic schema. This is critical for the n8n tool to read the result correctly.

4. Development & Iteration Process

The development involved a rigorous cycle focused on accuracy and stability:

Data Pre-processing: Created a robust method to clean and standardize the messy PDF text input, ensuring the LLM received clear, usable data.

Initial Agent Design: Built the core LangChain agent with a simple prompt and tested for baseline accuracy against a small set of manually screened resumes.

Prompt Refinement: Iteratively improved the system prompt and instructions to reduce common errors (e.g., focusing too much on irrelevant details, or being too generous with the score). This was the key stage for boosting classification accuracy.

Schema Enforcement: Implemented the Pydantic schema to eliminate formatting errors, moving the agent from prototype to a stable production tool.

Final Integration: Connected the LangChain service to the n8n workflow, creating the final, end-to-end automation loop.
