# AI Trip Planner-An Agentic Travel Assistant - LangChain & LanGraph

The AI Trip Planner is an intelligent, agentic travel assistant built using LangChain and Llama-based LLMs. It autonomously plans trips by reasoning step-by-step through your query, dynamically invoking specialized tools to gather accurate information — just like a human assistant would.

## Overview

This project transforms a Large Language Model into an **agentic travel assistant**, capable of reasoning, planning, and dynamically generating tailored trip plans. It combines:
- 🎯 Prompt engineering
- 🔧 External tools (weather, hotel search, etc.)
- 🌐 Optional API backend (FastAPI)
- 🖥️ Web UI (Streamlit)

## What Makes This Agentic?
This is not a simple chatbot.

This is an agentic AI system — a reasoning LLM embedded in a tool-rich environment, capable of:

Thinking in steps, deciding which tools to use and when

Executing actions autonomously (like fetching weather, finding places, converting currencies)

Synthesizing all outputs into a complete, personalized travel recommendation

All of this is orchestrated through LangChain's agent toolkit, where the LLM selects from a set of pre-defined tools based on the user's goal — without hardcoded flowcharts or templates.

## Agentic Architecture (LangGraph + LangChain)
What Happens
1. User Input:
You input destination, duration, budget, interests.

2. System Prompting:
The agent builds a message using prompt_library.prompt.SYSTEM_PROMPT.

3. LLM Reasoning:

The LLM is invoked via LangChain.

It decides whether it needs external data.

4. Tool Invocation:
Based on the request, the agent uses one or more tools:

WeatherInfoTool: Gets current or forecasted weather

PlaceSearchTool: Finds attractions

CurrencyConverterTool: Converts budget to local currency

CalculatorTool: Estimates total trip cost

5. Graph Loop (LangGraph):

Starts with agent node

If tools are required → calls ToolNode

Gets results → sends back to agent for final reply

Ends after response is ready

6. Output Delivery:

You get a customized, tool-enriched itinerary!
