# hindsight-smart-support
Context-aware AI customer support agent using Vectorize Hindsight persistent memory and Groq LLM inference.
<div align="center">

  # 🎧 Memory-Augmented Support Agent
  
  **Transforming customer support by eliminating amnesia using Vectorize Hindsight and Google Gemini.**

  [![Built for](https://img.shields.io/badge/Hackathon-Vectorize_Hindsight-blueviolet)](#)
  [![Memory Engine](https://img.shields.io/badge/Memory-Hindsight_Cloud-brightgreen)](#)
  [![LLM Inference](https://img.shields.io/badge/Powered_by-Google_Gemini-ff69b4)](#)
  [![Frontend](https://img.shields.io/badge/UI-Streamlit-red)](#)

</div>

---

## 💡 The Broken State of Customer Support

Customer support is the heartbeat of customer trust and loyalty, yet traditional chatbots fail because they forget. When customers reach out, they are treated like strangers and forced to re-explain their past tickets and known issues.

**The Cost of Forgetting:**
- 🔁 **The Amnesia Loop:** Customers waste time explaining the exact same issue multiple times.
- ⏳ **Wasted Time:** Support teams lose valuable minutes digging through fragmented CRM records.
- 🛑 **Resolution Delays:** Tickets escalate unnecessarily because past troubleshooting steps and fixes are not recalled.

> *"Nothing angers a customer more than repeating their story. An agent with full customer memory transforms the entire support experience."*

---

## ✨ The Solution: AI That Remembers & Adapts

Our **Memory-Augmented Support Agent** uses **Vectorize Hindsight** and **Google Gemini** to evolve from a generic, stateless chatbot into an intelligent, stateful companion. By embedding a persistent memory layer with over 24,000 ingested historical support memories[cite: 9], we instantly route past context directly into the AI's prompt.

1. **Retains Full Context:** The agent instantly recalls past tickets, hardware environments, and previous resolutions via Hindsight's retrieval API[cite: 6].
2. **Dynamic Customer Simulation:** Our Streamlit interface allows testers to simulate different customers (e.g., "Alex" or "Jane Doe") to see how the agent alters its response based on their unique history[cite: 4, 6].
3. **Accelerates Fixes:** The LLM bypasses basic triage and jumps straight to advanced troubleshooting by analyzing previous failed steps[cite: 5].

<div align="center">
  <!-- 🛑 PLACE YOUR MAIN DEMO VIDEO OR GIF LINK BELOW -->
  <img src="YOUR_MAIN_DEMO_VIDEO_URL_HERE.gif" alt="Agent Recalling Past Interactions" width="85%" />
  <p><em>Watch the agent instantly recall a user's previous ticket and adapt its troubleshooting steps.</em></p>
</div>

---

## ⚡ The Hindsight Difference (Before & After)

The shift from generic to personalized is what makes memory the centerpiece of our architecture.

<table width="100%">
  <tr>
    <td width="50%">
      <h3>❌ Without Memory (Standard Agent)</h3>
      <p><em>Gives the same canned response to everyone.</em></p>
      <ul>
        <li>Asks repetitive baseline questions ("What is your API key issue?").</li>
        <li>Suggests generic troubleshooting steps the user already tried.</li>
      </ul>
      <!-- 🛑 PLACE YOUR "STATELESS" DEMO VIDEO/GIF BELOW -->
      <img src="YOUR_STATELESS_DEMO_URL_HERE.gif" alt="Without Memory" width="100%" />
    </td>
    <td width="50%">
      <h3>✅ With Hindsight (Our Solution)</h3>
      <p><em>Recalls context, adapts intelligently, and solves problems faster.</em></p>
      <ul>
        <li>Cross-references current complaints with historical `ticket_id` data[cite: 6].</li>
        <li>Knows exactly what API issues the user faced previously[cite: 5].</li>
      </ul>
      <!-- 🛑 PLACE YOUR "HINDSIGHT MEMORY" DEMO VIDEO/GIF BELOW -->
      <img src="YOUR_MEMORY_DEMO_URL_HERE.gif" alt="With Memory" width="100%" />
    </td>
  </tr>
</table>

---

## 🏗️ System Architecture & Data Flow

Our system seamlessly connects a massive repository of simulated support data to a real-time conversational interface. 

```mermaid
graph TD
    A[Streamlit Web UI] -->|User Name & Issue| B(Python Backend app.py)
    B --> C{Vectorize Hindsight Client}
    C -->|Query customer_support_bank| D[(Memory Store: 24.5k+ Records)]
    D -->|Retrieves past tickets & metadata| C
    C -->|Context-Augmented Prompt| E[Google Gemini GenAI]
    E -->|Personalized Resolution| B
    B -->|Displays Chat Output| A
    
    F[Webhook / n8n Pipelines] -.->|Ingests Data| D
