# Crop Recommendation Agent

An AI-powered, multi-agent system built using **LangFlow**, **IBM watsonx.ai**, and **IBM Granite models** to deliver personalized crop recommendations and farming guidance to farmers, agricultural cooperatives, and agronomists.

---

## Problem Statement

### The Challenge
Farmers often struggle to decide which crops to grow due to varying soil conditions, unpredictable weather, water availability, and fluctuating market demand. Information about soil health, climate patterns, crop suitability, and best agricultural practices is scattered across unreliable or outdated sources. Without personalized, real-time guidance, many farmers face poor yields, resource wastage, and reduced profitability.

### The Objective
Build an AI-powered Crop Recommendation Agent that delivers personalized farming insights and guidance for farmers, agricultural cooperatives, and agronomists. The solution should:

- **Personalized Crop Plans** – Recommend crops based on soil type, pH, nutrient levels (N, P, K), rainfall, temperature, season, and land size.
- **Soil & Climate Data RAG Retrieval** – Fetch and summarize soil composition, weather forecasts, and market price data from reliable agricultural sources.
- **Field Monitoring & Feedback** – Allow farmers to log field conditions via text, images, or voice, and provide instant analysis on crop health and growth stage.
- **Preventive Farming Focus** – Suggest crop rotation plans, pest/disease management, and sustainable farming practices.
- **Visualization Dashboard** – Show soil health trends, predicted yield, seasonal crop performance, and progress toward sustainable farming goals.

---

## Proposed Solution

The proposed solution is a multi-agent AI-powered Crop Recommendation Agent built using LangFlow, IBM watsonx.ai, and Granite Models to provide personalized, real-time agricultural guidance.

At its core, the solution uses a **Retrieval-Augmented Generation (RAG)** pipeline to fetch accurate agricultural data from trusted sources such as government agricultural databases, soil health surveys, and weather/climate datasets. This data is embedded and stored in a vector database, enabling the system to retrieve and summarize soil composition, climate patterns, and crop suitability details using Granite models.

### Multi-Agent System

| Agent | Role |
|---|---|
| **Soil & Climate Knowledge Agent** | Retrieves and summarizes soil, weather, and market data using RAG |
| **Crop Recommendation Agent** | Generates personalized crop suggestions based on soil type, pH, NPK levels, rainfall, temperature, and land size |
| **Farming Advisory Agent** | Provides preventive farming suggestions — crop rotation, pest/disease management, sustainable soil practices |
| **Field Log & Feedback Agent** | Logs field conditions via text/voice/image and delivers instant crop health analysis |

A user-friendly dashboard (built with Streamlit or React) visualizes soil health trends, predicted yields, seasonal crop performance, and progress toward sustainable farming goals.

LangFlow orchestrates agent workflows, while watsonx.ai handles scalable model deployment, embeddings, and AI governance. Granite models power reasoning, summarization, and personalization.

---

## Role of Agentic AI

Agentic AI enables the Crop Recommendation Agent to function as an intelligent, autonomous system rather than a simple chatbot. Using IBM watsonx.ai and IBM Granite models, it coordinates multiple specialized agents to deliver personalized farming guidance.

Each agent performs a specific role — retrieving soil and climate data, generating crop recommendations, providing farming advisory, and analyzing field logs — while working collaboratively. This multi-agent approach ensures efficient task execution and accurate results.

Agentic AI also brings **context awareness**, understanding field details like soil type, location, season, and water availability to generate tailored recommendations. It supports **real-time adaptation**, continuously updating suggestions based on field conditions and weather changes, with agents communicating with each other for better decision-making.

Overall, Agentic AI makes the system proactive, personalized, and goal-driven — acting like a smart digital agronomist that helps farmers maximize yield and maintain sustainable farming practices.

---

## Key Differentiators

- **Multi-Agent Intelligence** – Specialized agents collaborate for accurate, context-aware crop guidance.
- **RAG-Based Accuracy** – Combines real-time data retrieval with AI generation to reduce misinformation.
- **Hyper-Personalization** – Recommendations tailored to soil type, climate, land size, and farmer preferences.
- **Real-Time Feedback Loop** – Adapts based on field logs, weather changes, and crop growth updates.
- **Multi-Modal Input** – Supports text, voice, and image-based field monitoring.
- **Preventive Farming Focus** – Pest management and sustainability-specific advice, not just crop selection.
- **Scalable & Enterprise-Ready** – Built on IBM watsonx.ai with IBM Granite models for reliability and governance.

---

## Architecture

The pipeline flows from chat input through three watsonx-powered agents and their tools, to chat output:

1. **Chat Input** – User enters field details, soil data, or queries (text/voice/image)
2. **Soil & Climate Knowledge Agent** (Granite-4.0-8B-Instruct) + **Search API tool** – fetches soil, weather, and market data
3. **Crop Recommendation Agent** (Granite-4.0-8B-Instruct) + **URL tool** – recommends suitable crops, expected yield, and planting time
4. **Farming Advisory Agent** (Granite-4.0-8B-Instruct) + **Calculator tool** – computes fertilizer/yield figures and gives a final farming plan
5. **Chat Output** – Displays the personalized crop recommendation and advisory

---

## Tech Stack

- **Orchestration**: LangFlow
- **AI Platform**: IBM watsonx.ai
- **Models**: IBM Granite (Granite-4.0-8B-Instruct)
- **Retrieval**: RAG pipeline with vector database

---

## Future Scope

1. **Integration with IoT & Field Sensors** – Connect with soil sensors, drones, and weather stations to collect real-time data such as soil moisture, temperature, humidity, and nutrient levels, enabling more accurate and dynamic recommendations based on actual field conditions.

2. **AI-Powered Voice Assistant & Multilingual Support** – Add a voice-enabled assistant with support for multiple regional languages, allowing farmers to interact in their preferred language and making the solution more inclusive for diverse rural populations.

---

## Setup

1. Clone this repository
2. Install dependencies (`myapp')
3. Configure environment variables:
   - `WATSONX_APIKEY``
   - `WATSONX_URL`
4. Import the LangFlow flow JSON and configure each agent with the IBM watsonx.ai provider and Granite model
5. Run the application

---

## License

This project was developed as part of an AI & Cloud internship/academic project using IBM watsonx.
