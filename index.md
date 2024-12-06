---
layout: default
title: Minecraft Server Steuerung
---

# Minecraft Server Steuerung

Willkommen! Hier kannst du deinen Minecraft-Server starten und stoppen.

<div class="controls">
    <button id="startButton">Server Starten</button>
    <button id="stopButton">Server Stoppen</button>
</div>

<div id="status">Status: Offline</div>

<script>
    // Funktionen zum Steuern des Serverstatus
    const statusElement = document.getElementById('status');
    const startButton = document.getElementById('startButton');
    const stopButton = document.getElementById('stopButton');

    startButton.addEventListener('click', () => {
        statusElement.textContent = "Status: Online";
        statusElement.style.color = "#4CAF50";
        alert("Der Server wurde gestartet!");
    });

    stopButton.addEventListener('click', () => {
        statusElement.textContent = "Status: Offline";
        statusElement.style.color = "#f44336";
        alert("Der Server wurde gestoppt!");
    });
</script>

<style>
    body {
        font-family: Arial, sans-serif;
        text-align: center;
        background-color: #1e1e1e;
        color: white;
        margin: 0;
        padding: 0;
    }
    h1 {
        margin-top: 20px;
    }
    button {
        font-size: 1.2em;
        padding: 10px 20px;
        margin: 20px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        transition: background-color 0.3s ease;
    }
    #startButton {
        background-color: #4CAF50;
        color: white;
    }
    #startButton:hover {
        background-color: #45a049;
    }
    #stopButton {
        background-color: #f44336;
        color: white;
    }
    #stopButton:hover {
        background-color: #e53935;
    }
    #status {
        margin-top: 30px;
        font-size: 1.5em;
    }
</style>
