<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>NextStep AI</title>

  <style>
    body {
      margin: 0;
      font-family: Arial;
      background: radial-gradient(circle at top, #0f172a, #020617);
      color: white;
    }

    header {
      display: flex;
      justify-content: space-between;
      padding: 20px 50px;
      background: rgba(255,255,255,0.05);
      backdrop-filter: blur(10px);
      position: sticky;
      top: 0;
    }

    header h1 {
      color: #38bdf8;
    }

    .hero {
      text-align: center;
      padding: 100px 20px;
    }

    .hero h2 {
      font-size: 50px;
      background: linear-gradient(90deg, #38bdf8, #a78bfa);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .chat-box {
      width: 90%;
      max-width: 500px;
      margin: 50px auto;
      background: rgba(255,255,255,0.05);
      padding: 20px;
      border-radius: 15px;
      backdrop-filter: blur(10px);
    }

    #chat {
      height: 250px;
      overflow-y: auto;
      border-bottom: 1px solid #334155;
      margin-bottom: 10px;
      padding-bottom: 10px;
    }

    input {
      width: 70%;
      padding: 10px;
      border: none;
      border-radius: 8px;
    }

    button {
      padding: 10px;
      border: none;
      border-radius: 8px;
      background: #38bdf8;
      cursor: pointer;
    }

    .msg {
      margin: 5px 0;
    }

    .user { color: #a78bfa; }
    .bot { color: #38bdf8; }
  </style>
</head>

<body>

<header>
  <h1>NextStep AI</h1>
</header>

<section class="hero">
  <h2>Your AI Future Starts Here</h2>
  <p>Build, learn, and grow with AI</p>
</section>

<div class="chat-box">
  <div id="chat"></div>
  <input id="input" placeholder="Ask something..." />
  <button onclick="send()">Send</button>
</div>

<script>
function send() {
  let input = document.getElementById("input");
  let chat = document.getElementById("chat");

  let userText = input.value;
  if (!userText) return;

  chat.innerHTML += `<div class='msg user'>You: ${userText}</div>`;

  let reply = getReply(userText.toLowerCase());

  chat.innerHTML += `<div class='msg bot'>AI: ${reply}</div>`;

  input.value = "";
  chat.scrollTop = chat.scrollHeight;
}

function getReply(text) {
  if (text.includes("hello")) return "Hi! I’m NextStep AI 🤖";
  if (text.includes("who are you")) return "I’m your mini AI assistant built inside this website.";
  if (text.includes("help")) return "Ask me anything about learning or projects!";
  return "I’m still learning... try asking something simple 😊";
}
</script>

</body>
</html>
