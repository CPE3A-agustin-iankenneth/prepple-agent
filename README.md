# Prepple Agent

This is the AI Voice Agent component for **Prepple**, an automated HR interview platform. It is designed to conduct autonomous initial screening interviews with candidates.

This agent is used in conjunction with the main Prepple application:
👉 **[Prepple AI Repository](https://github.com/CPE3A-agustin-iankenneth/prepple-ai)**

## Overview

The Prepple Agent is built using [LiveKit Agents](https://github.com/livekit/agents-js) and integrates with various AI services to provide a seamless interview experience.

### Key Features

-   **Autonomous Interviews**: Conducts voice-based interviews based on job descriptions and custom instructions.
-   **Resume Parsing**: Analyzes candidate resumes (PDF/DOCX) to tailor interview questions.
-   **Real-time Interaction**: Uses LiveKit for low-latency voice communication.
-   **AI Intelligence**: Powered by Google Gemini (via `@livekit/agents-plugin-google`) for natural language understanding and generation.
-   **Turn Detection**: Utilizes Silero VAD and LiveKit Turn Detector for natural conversation flow.

## Tech Stack

-   **Framework**: Node.js, LiveKit Agents
-   **AI Models**: Google Gemini (LLM), Deepgram/Google (STT/TTS via LiveKit plugins)
-   **Tools**: `pdf-parse`, `mammoth` (for document parsing)

## Development Setup

### Prerequisites

-   Node.js >= 22.0.0
-   pnpm >= 10.0.0
-   LiveKit Cloud account (or self-hosted)

### Installation

1.  Clone the repository:
    ```bash
    git clone <your-repo-url>
    cd prepple-agent
    ```

2.  Install dependencies:
    ```bash
    pnpm install
    ```

3.  Set up environment variables:
    Copy `.env.example` to `.env.local` and fill in your LiveKit credentials:
    ```env
    LIVEKIT_URL=...
    LIVEKIT_API_KEY=...
    LIVEKIT_API_SECRET=...
    ```

### Running the Agent

1.  **Download required models** (first time only):
    ```bash
    pnpm run download-files
    ```

2.  **Start in development mode**:
    ```bash
    pnpm run dev
    ```

3.  **Production build**:
    ```bash
    pnpm run build
    pnpm run start
    ```

## Deployment

This project includes a `Dockerfile` for containerized deployment. Refer to the [LiveKit Deployment Guide](https://docs.livekit.io/agents/ops/deployment/) for more details.

## License

This project is licensed under the MIT License.

