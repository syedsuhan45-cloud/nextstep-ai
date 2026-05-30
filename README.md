<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>NextStep AI</title>

<style>
body {
  margin: 0;
  font-family: Arial;
  background: radial-gradient(circle at top, #0b1220, #020617);
  color: white;
}

/* HEADER */
header {
  padding: 18px 30px;
  display: flex;
  justify-content: space-between;
  background: rgba(255,255,255,0.05);
  backdrop-filter: blur(12px);
  position: sticky;
  top: 0;
}

header h1 {
  color: #38bdf8;
}

/* HERO */
.hero {
  text-align: center;
  padding: 60px 20px 20px;
}

.hero h2 {
  font-size: 42px;
  background: linear-gradient(90deg,#38bdf8,#a78bfa);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* CHAT BOX */
.chat-container {
  width: 92%;
  max-width: 650px;
  margin: auto;
  margin-top: 20px;
  background: rgba(255,255,255,0.05);
  border-radius: 16px;
  padding: 15px;
  backdrop-filter: blur(12px);
  box-shadow: 0 0 30px rgba(56,189,248,0.1);
}

#chat {
  height: 320px;
  overflow-y: auto;
  padding: 10px;
}

/* MESSAGES */
.msg {
  margin: 10px 0;
  line-height: 1.4;
}

.user {
  color: #a78bfa;
}

.ai {
  color: #38bdf8;
}

/* INPUT */
.input-box {
  display: flex;
  gap: 10px;
  margin-top: 10px;
}

input {
  flex: 1;
  padding: 12px;
  border-radius: 10px;
  border: none;
  outline: none;
}

button {
  padding: 12px 18px;
  border: none;
  border-radius: 10px;
  background: #38bdf8;
  cursor: pointer;
  font-weight: bold;
}

button:hover {
  background: #0ea5e9;
}

/* FOOTER */
footer {
  text-align: center;
  margin-top: 40px;
  padding: 20px;
  color: #94a3b8;
}

.credit {
  color: #38bdf8;
  margin-top: 5px;
}

/* ANIMATION */
@keyframes fade {
  from {opacity: 0; transform: translateY(5px);}
  to {opacity: 1; transform: translateY(0);}
}

.msg {
  animation: fade 0.3s ease-in-out;
}
</style>
</head>

<body>

<header>
  <h1>NextStep AI</h1>
</header>

<section class="hero">
  <h2>Your AI Future Starts Here</h2>
  <p>Ultra Premium AI Assistant for learning, building & growth</p>
</section>

<div class="chat-container">
  <div id="chat"></div>

  <div class="input-box">
    <input id="input" placeholder="Ask NextStep AI..." />
    <button onclick="send()">Send</button>
  </div>
</div>

<footer>
  © 2026 NextStep AI
  <div class="credit">Built by Suhan</div>
</footer>

<script>
function addMessage(text, type) {
  let chat = document.getElementById("chat");
  chat.innerHTML += `<div class='msg ${type}'>${text}</div>`;
  chat.scrollTop = chat.scrollHeight;
}

/* FAKE AI (safe version for now) */
function send() {
  let input = document.getElementById("input");
  let text = input.value;
  if (!text) return;

  addMessage("You: " + text, "user");

  setTimeout(() => {
    addMessage("NextStep AI: I’m your premium assistant. Real AI will be connected next 🚀", "ai");
  }, 600);

  input.value = "";
}
</script>

</body>
</html>
