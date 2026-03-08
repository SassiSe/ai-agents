<div align="center">

# 🧠 Ollama + OpenClaw on a VPS

### *Cloud-hosted AI agent when local GPU isn't an option*

---

> ⚠️ **Important:** The ollama model does not run locally — requests and data are sent to the servers of the selected model provider.

| 💡 | This setup is for **exploring AI bot capabilities** while hardware is limited. |
|---|---|
| 🎯 | The goal is to **upgrade the GPU** and run the model fully on-premise. |

</div>

---

## 📦 1. Infrastructure

| Resource | Spec |
|----------|------|
| vCPU | 12 |
| RAM | 48 GB |

---

## 🔧 2. Install OpenClaw

Install the OpenClaw CLI:

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

Run the onboarding wizard and install the daemon:

```bash
openclaw onboard --install daemon
```

> Accept the risk prompt and keep the current model. No additional configuration needed at this stage.

---

## 🦙 3. Set Up Ollama

Install Ollama:

```bash
curl -fsSL https://ollama.com/install.sh | sh
```

Log in with your Ollama account (create one if you don't have one yet):

```bash
ollama login
```

✅ Click the webpage link that appears and confirm **Connect Device** on the Ollama dashboard.

### 🔑 Create an API Key

1. Navigate to **Keys** in your Ollama account settings.
2. Create a new API token and give it a descriptive name.
3. Copy the token somewhere accessible.

Export the token as an environment variable:

```bash
export OLLAMA_API_KEY=abcdefghijklmnopqrstuvwxyz
```

### 🚀 Launch a Model

Launch the model of your choice (example uses `kimi-k2.5`):

```bash
ollama launch openclaw --model kimi-k2.5:cloud
```

---

## 🤖 4. Connect a Telegram Bot

Re-run the onboarding wizard:

```bash
openclaw onboard --install daemon
```

1. Select **Telegram** as the integration.
2. Open Telegram and send `/newbot` to **@BotFather**.
3. Copy the bot token you receive and paste it as the **Telegram token** in OpenClaw.

### ✅ Approve the Pairing

Go to your bot in Telegram — you'll see an approval command. Run it:

```bash
openclaw pairing approve telegram ABCDEFG
```

<div align="center">

### 🎉 You now have a functioning personal AI bot!

</div>

---

## 🗺️ Future Steps

- [ ] Configure the `skill.md` file in the workspace
- [ ] Upgrade infrastructure to run the model locally (GPU)
