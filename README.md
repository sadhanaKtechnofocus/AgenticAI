# AgenticAI
Build and Deploy Azure AI Agents App with GitHub Code spaces

# Tutorial Overview
Learn to build, modify, and deploy an Azure AI-powered application using GitHub Codespaces. This tutorial simplifies the Get Started with AI Agents repo to focus on GitHub Codespaces-based development.

# Prerequisites
GitHub account with Codespaces access
Azure subscription (student credits work)

## Step 1: Launch the Project in Codespaces
Fork the repo: get-started-with-ai-agents
Open your fork in Codespaces:
Go to your repo > Code > Codespaces tab > Create codespace
Wait for setup to complete.

## Step 2: Configure Azure in Codespaces
Login to Azure: bash az login
Initialize project: bash azd init --template . --environment aiagents-env

## Step 3: Deploy to Azure
Provision and deploy resources: bash azd up
Copy the deployed app URL shown in the output.

## Step 4: Explore and Modify the App

### Task 1: Change the AI Agent's Personality
Open /src/agents/agent.ts
Find and change: ts const systemMessage = "You are a helpful assistant."; To: ts const systemMessage = "You are a fitness coach who provides workout tips and motivation.";
Save and redeploy: bash azd deploy

### Task 2: Add a Custom Command (e.g., Jokes)
In /src/agents/agent.ts, add: ts if (userInput.toLowerCase().includes("joke")) { return "Why did the developer go broke? Because they used up all their cache!"; }
Save and redeploy.

### Task 3: Customize the Web UI
Open /src/web/app/pages/index.tsx
Change heading and button: ```tsx
Welcome to Your Personal AI Buddy!
<button className="bg-blue-500 text-white">Chat Now</button> 3. Save and preview:bash npm run dev 4. Redeploy:bash azd deploy ```

### Task 4: Add Input Field for Agent Name
In /src/web/app/pages/index.tsx, add: ```tsx const [agentName, setAgentName] = useState("AI Buddy"); <input type="text" value={agentName} onChange={(e) => setAgentName(e.target.value)} placeholder="Enter your AI's name" className="border p-2 rounded" />
{agentName} is ready to chat!
``` 2. Save and redeploy.

## Step 5: Test Your App
Visit the Azure Web App URL from deployment.
Try different inputs (e.g., ask for a joke or fitness tip).
Monitor logs: bash azd monitor

## Step 6: Clean Up (Optional)
azd down
Happy coding!
