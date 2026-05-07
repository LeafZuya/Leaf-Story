<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>Pohon Pesona - Gantung Pesan dengan Nama & 20 Warna + RGB Custom</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
            background: #2b5f3b;
            min-height: 100vh;
        }

        .sky {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(180deg, #1e6ec5 0%, #6fc5e6 50%, #b0e0ff 100%);
            z-index: 0;
            overflow: hidden;
        }

        .mountains {
            position: absolute;
            bottom: 150px;
            left: 0;
            width: 100%;
            height: 250px;
            z-index: 1;
        }
        .mountain {
            position: absolute;
            bottom: 0;
            width: 0;
            height: 0;
            border-left: 180px solid transparent;
            border-right: 180px solid transparent;
            border-bottom: 200px solid #5d7a5c;
        }
        .m1 { left: -5%; border-bottom-color: #4a6741; transform: scale(0.9);}
        .m2 { left: 25%; border-bottom-color: #3d5a3a; transform: scale(1.2);}
        .m3 { left: 55%; border-bottom-color: #557a4a; transform: scale(1);}
        .m4 { left: 80%; border-bottom-color: #4a6b3f; transform: scale(1.1);}

        .ground {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 180px;
            background: linear-gradient(180deg, #5d8c48 0%, #3d6b2e 100%);
            z-index: 2;
        }
        .grass {
            position: absolute;
            bottom: 180px;
            left: 0;
            width: 100%;
            height: 20px;
            background: #6aa34d;
            border-radius: 20px 20px 0 0;
        }

        .river {
            position: absolute;
            bottom: 50px;
            left: 0;
            width: 100%;
            height: 55px;
            background: linear-gradient(90deg, #3a7ca5, #5fa8d3, #3a7ca5);
            z-index: 3;
            opacity: 0.85;
            box-shadow: inset 0 3px 10px rgba(0,0,0,0.2);
        }
        .river-flow {
            position: absolute;
            top: 20px;
            left: 0;
            width: 200%;
            height: 3px;
            background: rgba(255,255,255,0.6);
            animation: flowAnim 4s linear infinite;
        }
        @keyframes flowAnim {
            0% { transform: translateX(-50%); }
            100% { transform: translateX(50%); }
        }

        .sun {
            position: absolute;
            top: 50px;
            right: 70px;
            width: 90px;
            height: 90px;
            background: radial-gradient(circle, #FFD700, #FFA500);
            border-radius: 50%;
            box-shadow: 0 0 50px rgba(255, 200, 50, 0.9);
            z-index: 5;
            animation: sunBeat 2s infinite alternate;
        }
        @keyframes sunBeat {
            0% { transform: scale(1); box-shadow: 0 0 30px rgba(255,200,50,0.6);}
            100% { transform: scale(1.05); box-shadow: 0 0 70px rgba(255,220,70,1);}
        }
        .sun-rays {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 150px;
            height: 150px;
            background: radial-gradient(circle, rgba(255,215,0,0.3) 0%, rgba(255,215,0,0) 70%);
            border-radius: 50%;
            transform: translate(-50%, -50%);
            animation: spinRays 10s linear infinite;
        }
        @keyframes spinRays {
            0% { transform: translate(-50%, -50%) rotate(0deg); opacity: 0.8;}
            100% { transform: translate(-50%, -50%) rotate(360deg); opacity: 1;}
        }

        .cloud {
            position: absolute;
            background: rgba(255, 255, 245, 0.95);
            border-radius: 1000px;
            z-index: 5;
            animation: cloudDrift linear infinite;
            filter: drop-shadow(2px 4px 8px rgba(0,0,0,0.1));
        }
        @keyframes cloudDrift {
            0% { transform: translateX(-150%); }
            100% { transform: translateX(calc(100vw + 200%)); }
        }

        .main-container {
            position: relative;
            z-index: 20;
            width: 100%;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            pointer-events: none;
        }

        .dashboard {
            pointer-events: auto;
            background: rgba(20, 25, 15, 0.85);
            backdrop-filter: blur(16px);
            border-radius: 60px;
            margin: 20px;
            padding: 14px 28px;
            display: flex;
            flex-wrap: wrap;
            gap: 18px;
            justify-content: center;
            align-items: center;
            color: #fef5e0;
            font-weight: 600;
            border: 1px solid #ffdd99;
            box-shadow: 0 8px 20px rgba(0,0,0,0.4);
            z-index: 30;
        }
        .btn {
            background: #ffb347;
            border: none;
            padding: 10px 26px;
            border-radius: 40px;
            font-weight: bold;
            cursor: pointer;
            transition: 0.2s;
            font-family: 'Inter', sans-serif;
        }
        .btn-primary {
            background: #6fbf2c;
            color: #1f3a1a;
        }
        .btn-primary:hover {
            background: #8ed653;
            transform: scale(1.02);
        }
        .counter-info {
            background: #2c2b1cd9;
            padding: 7px 20px;
            border-radius: 50px;
            font-size: 0.9rem;
        }

        .tree-wrapper {
            pointer-events: auto;
            position: relative;
            width: 100%;
            max-width: 950px;
            margin: 20px auto;
            display: flex;
            justify-content: center;
            cursor: crosshair;
        }
        .tree-canvas {
            width: 100%;
            max-width: 750px;
            filter: drop-shadow(12px 20px 20px rgba(0,0,0,0.4));
        }

        .message-card {
            position: absolute;
            width: 4px;
            height: 4px;
            border-radius: 1px;
            cursor: pointer;
            transition: all 0.25s cubic-bezier(0.34, 1.2, 0.64, 1);
            box-shadow: 0 0 2px rgba(0,0,0,0.5);
            z-index: 100;
            pointer-events: auto;
            opacity: 0.9;
        }
        .message-card:hover {
            transform: scale(1.3);
            box-shadow: 0 0 5px gold;
            z-index: 101;
        }

        .read-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.85);
            backdrop-filter: blur(12px);
            z-index: 2000;
            display: flex;
            align-items: center;
            justify-content: center;
            visibility: hidden;
            opacity: 0;
            transition: 0.2s;
        }
        .read-modal.active {
            visibility: visible;
            opacity: 1;
        }
        .paper-animate {
            background: #fffef5;
            width: 90%;
            max-width: 580px;
            max-height: 80vh;
            border-radius: 28px;
            padding: 25px;
            animation: paperOpen 0.45s cubic-bezier(0.34, 1.2, 0.64, 1);
            transform-origin: center;
            box-shadow: 0 30px 50px rgba(0,0,0,0.5);
        }
        @keyframes paperOpen {
            0% { transform: scale(0) rotate(-8deg); opacity: 0; }
            60% { transform: scale(1.05) rotate(1deg); }
            100% { transform: scale(1) rotate(0); opacity: 1; }
        }
        .scroll-paper {
            overflow-y: auto;
            max-height: 50vh;
            padding: 20px;
            background: #fff7e8;
            border-radius: 20px;
            font-size: 1rem;
            line-height: 1.65;
            white-space: pre-wrap;
        }
        .author-name {
            font-size: 0.85rem;
            color: #a0522d;
            margin-top: 12px;
            font-style: italic;
            border-top: 1px dashed #d4b48c;
            padding-top: 10px;
        }
        .btn-lime {
            background: #b5ff5a;
            color: #1f4a1a;
            border: none;
            padding: 12px;
            border-radius: 60px;
            font-weight: bold;
            font-size: 1rem;
            cursor: pointer;
            transition: 0.1s;
            width: 100%;
            margin-top: 18px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }
        .btn-lime:hover { background: #d0ff85; transform: scale(0.98); }

        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.7);
            backdrop-filter: blur(8px);
            z-index: 1000;
            display: flex;
            align-items: center;
            justify-content: center;
            visibility: hidden;
            opacity: 0;
            transition: 0.2s;
        }
        .modal.active {
            visibility: visible;
            opacity: 1;
        }
        .modal-card {
            background: #fffaf2;
            width: 90%;
            max-width: 550px;
            border-radius: 48px;
            padding: 30px;
            box-shadow: 0 20px 40px black;
            max-height: 90vh;
            overflow-y: auto;
        }
        .color-grid {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            gap: 10px;
            margin: 15px 0;
        }
        .color-option {
            width: 100%;
            aspect-ratio: 1;
            border-radius: 16px;
            cursor: pointer;
            border: 3px solid white;
            transition: 0.1s;
            box-shadow: 0 2px 6px rgba(0,0,0,0.2);
        }
        .color-option.selected {
            transform: scale(1.05);
            border-color: gold;
            box-shadow: 0 0 0 2px #ffd700;
        }
        .custom-rgb {
            background: #f0f0f0;
            padding: 15px;
            border-radius: 24px;
            margin: 15px 0;
        }
        .rgb-inputs {
            display: flex;
            gap: 10px;
            margin-top: 10px;
            flex-wrap: wrap;
        }
        .rgb-inputs input {
            flex: 1;
            padding: 8px;
            border-radius: 20px;
            border: 1px solid #c2a575;
        }
        .preview-box {
            width: 50px;
            height: 50px;
            border-radius: 12px;
            border: 2px solid #ddd;
            margin-top: 10px;
        }
        textarea, input[type="text"] {
            width: 100%;
            border-radius: 28px;
            padding: 15px;
            font-family: inherit;
            border: 1px solid #d4b48c;
            font-size: 1rem;
        }
        .char-counter { font-size: 0.8rem; text-align: right; margin-top: 5px; color: #5a4a2e; }
        
        .star-explode {
            position: fixed;
            pointer-events: none;
            animation: starBoom 0.5s ease-out forwards;
            z-index: 9999;
        }
        @keyframes starBoom {
            0% { transform: scale(0); opacity: 1; background: radial-gradient(circle, gold, #ffcc44);}
            100% { transform: scale(3.5); opacity: 0; background: radial-gradient(circle, #fff0a0, transparent);}
        }
        footer {
            text-align: center;
            color: white;
            padding: 15px;
            font-weight: 500;
            text-shadow: 1px 1px 3px black;
            z-index: 20;
            pointer-events: none;
            font-size: 0.8rem;
        }
    </style>
</head>
<body>
<div class="sky">
    <div class="sun"><div class="sun-rays"></div></div>
    <div class="mountains"><div class="mountain m1"></div><div class="mountain m2"></div><div class="mountain m3"></div><div class="mountain m4"></div></div>
    <div class="ground"></div><div class="grass"></div>
    <div class="river"><div class="river-flow"></div></div>
</div>

<div class="main-container">
    <div class="dashboard">
        <span><i class="fas fa-tree"></i> 🌳 Pohon Raksasa Nusantara</span>
        <span class="counter-info" id="dailyCountDisplay">📜 0/3 Pesan Hari Ini</span>
        <button class="btn btn-primary" id="newMessageBtn"><i class="fas fa-feather-alt"></i> Gantung Pesan</button>
        <button class="btn" id="refreshBtn"><i class="fas fa-sync-alt"></i> Segarkan</button>
    </div>
    
    <div class="tree-wrapper" id="treeWrapper">
        <svg class="tree-canvas" viewBox="0 0 700 800" xmlns="http://www.w3.org/2000/svg">
            <defs>
                <radialGradient id="leafMain" cx="45%" cy="45%">
                    <stop offset="0%" stop-color="#6fbf4c"/>
                    <stop offset="100%" stop-color="#2d7530"/>
                </radialGradient>
                <radialGradient id="leafSec" cx="50%" cy="50%">
                    <stop offset="0%" stop-color="#5fa842"/>
                    <stop offset="100%" stop-color="#1f5a22"/>
                </radialGradient>
            </defs>
            <path d="M320 800 Q330 650 325 500 Q318 380 330 320 L370 320 Q382 380 375 500 Q370 650 380 800 Z" fill="#5d3a1a" stroke="#3e2812" stroke-width="4"/>
            <path d="M315 580 Q345 560 375 575 Q385 590 385 650 Q345 630 315 650 Z" fill="#6b4226"/>
            <path d="M335 360 Q280 290 210 240 Q255 265 295 290 Z" fill="#5a3a1a"/>
            <path d="M365 360 Q430 280 510 230 Q450 265 405 300 Z" fill="#5a3a1a"/>
            <circle cx="240" cy="250" r="78" fill="url(#leafMain)" opacity="0.95"/>
            <circle cx="460" cy="240" r="80" fill="url(#leafMain)" opacity="0.95"/>
            <circle cx="350" cy="200" r="95" fill="url(#leafMain)"/>
            <circle cx="300" cy="160" r="72" fill="url(#leafSec)"/>
            <circle cx="410" cy="165" r="75" fill="url(#leafSec)"/>
            <circle cx="350" cy="110" r="85" fill="#4bae3a"/>
            <circle cx="260" cy="310" r="65" fill="#52b446"/>
            <circle cx="440" cy="300" r="67" fill="#52b446"/>
            <circle cx="190" cy="275" r="55" fill="#3f9a33"/>
            <circle cx="510" cy="265" r="55" fill="#3f9a33"/>
            <circle cx="350" cy="80" r="68" fill="#5bbe48"/>
            <circle cx="305" cy="55" r="52" fill="#68cc54"/>
            <circle cx="395" cy="58" r="54" fill="#68cc54"/>
            <!-- Buah -->
            <circle cx="210" cy="270" r="13" fill="#FF6347" stroke="#cc3b1f" stroke-width="2"/>
            <circle cx="490" cy="250" r="14" fill="#FFA500" stroke="#d97a00"/>
            <circle cx="320" cy="140" r="12" fill="#FF4500"/>
            <circle cx="390" cy="100" r="13" fill="#F4A261"/>
            <circle cx="280" cy="190" r="11" fill="#E63946"/>
            <circle cx="440" cy="210" r="12" fill="#F4D03F"/>
            <circle cx="360" cy="280" r="11" fill="#FFB347"/>
            <circle cx="170" cy="295" r="10" fill="#E76F51"/>
            <circle cx="530" cy="280" r="11" fill="#FFD700"/>
        </svg>
        <div id="messagesContainer" style="position: absolute; top:0; left:0; width:100%; height:100%; pointer-events: none;"></div>
    </div>
    <footer>🍃 Klik pohon untuk menggantung pesan (kartu kecil 4x4px). Klik kartu untuk membaca dengan animasi kertas terbuka ✨</footer>
</div>

<!-- Modal Buat Pesan Baru dengan Nama & 20 Warna + RGB Custom -->
<div id="createModal" class="modal">
    <div class="modal-card">
        <h3><i class="fas fa-leaf"></i> Gantung Pesanmu</h3>
        <input type="text" id="authorName" placeholder="Nama penulis / nickname" maxlength="50" style="margin-bottom: 12px;">
        <textarea id="messageInput" rows="4" maxlength="500" placeholder="Tulis pesanmu di sini (maks 500 karakter)..."></textarea>
        <div class="char-counter"><span id="charCountNow">0</span>/500</div>
        
        <div style="margin: 15px 0 5px 0; font-weight: 600;">🎨 20 Warna Kartu:</div>
        <div class="color-grid" id="colorGrid"></div>
        
        <div class="custom-rgb">
            <div style="font-weight: 600;">✨ Atau Warna Custom (RGB / Hex)</div>
            <div class="rgb-inputs">
                <input type="number" id="rVal" placeholder="R 0-255" min="0" max="255">
                <input type="number" id="gVal" placeholder="G 0-255" min="0" max="255">
                <input type="number" id="bVal" placeholder="B 0-255" min="0" max="255">
                <input type="text" id="hexVal" placeholder="#RRGGBB" maxlength="7">
            </div>
            <div style="display: flex; align-items: center; gap: 15px; margin-top: 10px;">
                <div class="preview-box" id="customPreview" style="background: #c7e9b0;"></div>
                <button id="applyCustomBtn" class="btn" style="padding: 8px 20px;">Gunakan Warna Ini</button>
            </div>
        </div>
        
        <button id="pickLocationBtn" class="btn-primary" style="width:100%; margin-top: 12px;">📍 Klik di Pohon untuk Menentukan Posisi</button>
        <button id="cancelCreateBtn" style="margin-top: 10px; background:#ccc;">Batal</button>
        <input type="hidden" id="selectedCardColor" value="#c7e9b0">
    </div>
</div>

<!-- Modal Baca Pesan -->
<div id="readModal" class="read-modal">
    <div class="paper-animate">
        <h3><i class="fas fa-envelope-open-text"></i> Pesan dari Ranting</h3>
        <div class="scroll-paper" id="messageFullContent"></div>
        <div class="author-name" id="messageAuthor"></div>
        <button id="closeReadButton" class="btn-lime"><i class="fas fa-star"></i> Selesai Baca ✨</button>
    </div>
</div>

<script>
    // 20 Warna Premium
    const colorPalette20 = [
        "#c7e9b0", "#ffffff", "#a2d9ff", "#ffe69b", "#ffb7b2",
        "#d4f1f9", "#fde2c4", "#e0bbe4", "#b5ead7", "#ffd1dc",
        "#c5e0b4", "#ffcc99", "#b3cde0", "#f4c3b0", "#9ad0f5",
        "#f5b0cb", "#c7e9c0", "#ffb347", "#a8e6cf", "#dab6fc"
    ];
    
    let allMessages = [];
    const currentUserId = localStorage.getItem("visitorId") || 'user_' + Math.random().toString(36).substr(2, 10);
    localStorage.setItem("visitorId", currentUserId);
    
    let todayStr = new Date().toISOString().slice(0,10);
    let userDailyCount = 0;
    
    function loadMessages() {
        const stored = localStorage.getItem("treeMessagesV3");
        if(stored) allMessages = JSON.parse(stored);
        else allMessages = [];
        renderSmallCards();
    }
    function saveMessages() { localStorage.setItem("treeMessagesV3", JSON.stringify(allMessages)); }
    
    function updateDailyLimit() {
        const lastDate = localStorage.getItem(`lastDate_${currentUserId}`);
        const storedCount = localStorage.getItem(`count_${currentUserId}`);
        const now = new Date().toISOString().slice(0,10);
        if(lastDate !== now) {
            localStorage.setItem(`lastDate_${currentUserId}`, now);
            localStorage.setItem(`count_${currentUserId}`, "0");
            userDailyCount = 0;
        } else {
            userDailyCount = storedCount ? parseInt(storedCount) : 0;
        }
        document.getElementById("dailyCountDisplay").innerHTML = `📜 ${userDailyCount}/3 Pesan Hari Ini`;
    }
    function incrementDaily() {
        userDailyCount++;
        localStorage.setItem(`count_${currentUserId}`, userDailyCount);
        updateDailyLimit();
    }
    function canPostMessage() { return userDailyCount < 3; }
    
    function renderSmallCards() {
        const container = document.getElementById("messagesContainer");
        container.innerHTML = "";
        allMessages.forEach(msg => {
            const card = document.createElement("div");
            card.className = "message-card";
            if(msg.color && msg.color.includes("gradient")) card.style.background = msg.color;
            else card.style.backgroundColor = msg.color || "#c7e9b0";
            card.style.left = `calc(${msg.x * 100}% - 2px)`;
            card.style.top = `calc(${msg.y * 100}% - 2px)`;
            card.style.width = "4px";
            card.style.height = "4px";
            card.setAttribute("data-id", msg.id);
            card.onclick = (e) => { e.stopPropagation(); openReadMessage(msg); };
            container.appendChild(card);
        });
    }
    
    function openReadMessage(msg) {
        const modal = document.getElementById("readModal");
        const contentDiv = document.getElementById("messageFullContent");
        const authorDiv = document.getElementById("messageAuthor");
        contentDiv.innerHTML = `<div style="white-space: pre-wrap;">${escapeHtml(msg.text)}</div>`;
        authorDiv.innerHTML = `✍️ Ditulis oleh: ${escapeHtml(msg.author || 'Anonim')}`;
        modal.classList.add("active");
        
        const closeBtn = document.getElementById("closeReadButton");
        const newClose = closeBtn.cloneNode(true);
        closeBtn.parentNode.replaceChild(newClose, closeBtn);
        newClose.onclick = () => {
            const star = document.createElement("div");
            star.className = "star-explode";
            star.style.width = "50px";
            star.style.height = "50px";
            star.style.borderRadius = "50%";
            star.style.top = "50%";
            star.style.left = "50%";
            star.style.transform = "translate(-50%, -50%)";
            document.body.appendChild(star);
            setTimeout(() => star.remove(), 500);
            modal.classList.remove("active");
        };
    }
    
    function escapeHtml(str) { 
        return str.replace(/[&<>]/g, (m) => ({'&':'&amp;','<':'&lt;','>':'&gt;'})[m]); 
    }
    
    let pendingMessageData = null;
    let isSelectingPosition = false;
    const treeWrapper = document.getElementById("treeWrapper");
    
    function startPositionSelection() {
        if(!canPostMessage()) {
            alert("⚠️ Kamu sudah menggantung 3 pesan hari ini. Reset besok!");
            return;
        }
        isSelectingPosition = true;
        treeWrapper.style.cursor = "crosshair";
        alert("✨ Sekarang klik pada area pohon (batang, daun) untuk menggantung pesanmu ✨\n(Pesan akan muncul sebagai titik 4x4px)");
    }
    
    treeWrapper.addEventListener("click", (e) => {
        if(!isSelectingPosition || !pendingMessageData) return;
        const rect = treeWrapper.getBoundingClientRect();
        let x = (e.clientX - rect.left) / rect.width;
        let y = (e.clientY - rect.top) / rect.height;
        x = Math.min(0.94, Math.max(0.06, x));
        y = Math.min(0.88, Math.max(0.12, y));
        
        let finalColor = pendingMessageData.color;
        if(finalColor === "gradient") finalColor = "linear-gradient(135deg, #fad0c4, #ffdde1)";
        
        const newMsg = {
            id: Date.now() + Math.random(),
            text: pendingMessageData.text,
            author: pendingMessageData.author || "Anonim",
            color: finalColor,
            x: x, y: y,
            userId: currentUserId,
            timestamp: Date.now(),
            date: todayStr
        };
        allMessages.push(newMsg);
        saveMessages();
        incrementDaily();
        renderSmallCards();
        
        isSelectingPosition = false;
        treeWrapper.style.cursor = "default";
        pendingMessageData = null;
        document.getElementById("createModal").classList.remove("active");
    });
    
    // Render 20 color options
    let selectedColorVal = "#c7e9b0";
    function buildColorGrid() {
        const grid = document.getElementById("colorGrid");
        grid.innerHTML = "";
        colorPalette20.forEach(col => {
            const div = document.createElement("div");
            div.className = "color-option";
            div.style.backgroundColor = col;
            div.setAttribute("data-color", col);
            div.onclick = () => {
                document.querySelectorAll(".color-option").forEach(opt => opt.classList.remove("selected"));
                div.classList.add("selected");
                selectedColorVal = col;
                document.getElementById("selectedCardColor").value = col;
            };
            grid.appendChild(div);
        });
        // pilih default pertama
        grid.children[0]?.classList.add("selected");
    }
    
    // RGB Custom Logic
    function applyCustomColor() {
        let r = parseInt(document.getElementById("rVal").value);
        let g = parseInt(document.getElementById("gVal").value);
        let b = parseInt(document.getElementById("bVal").value);
        let hex = document.getElementById("hexVal").value.trim();
        let finalColor = "";
        if(hex && /^#[0-9A-Fa-f]{6}$/.test(hex)) {
            finalColor = hex;
            // update RGB fields based on hex
            const rVal = parseInt(hex.slice(1,3),16);
            const gVal = parseInt(hex.slice(3,5),16);
            const bVal = parseInt(hex.slice(5,7),16);
            if(!isNaN(rVal)) document.getElementById("rVal").value = rVal;
            if(!isNaN(gVal)) document.getElementById("gVal").value = gVal;
            if(!isNaN(bVal)) document.getElementById("bVal").value = bVal;
        } else if(!isNaN(r) && !isNaN(g) && !isNaN(b) && r>=0 && r<=255 && g>=0 && g<=255 && b>=0 && b<=255) {
            finalColor = `rgb(${r}, ${g}, ${b})`;
            const hexCode = "#" + ((1 << 24) + (r << 16) + (g << 8) + b).toString(16).slice(1);
            document.getElementById("hexVal").value = hexCode.toUpperCase();
        } else {
            alert("Masukkan nilai RGB (0-255) atau Hex valid (#RRGGBB)");
            return;
        }
        document.getElementById("customPreview").style.backgroundColor = finalColor;
        selectedColorVal = finalColor;
        document.getElementById("selectedCardColor").value = finalColor;
        // Hapus seleksi dari grid custom
        document.querySelectorAll(".color-option").forEach(opt => opt.classList.remove("selected"));
        alert(`Warna custom ${finalColor} dipilih!`);
    }
    
    function updatePreviewFromRGB() {
        let r = parseInt(document.getElementById("rVal").value);
        let g = parseInt(document.getElementById("gVal").value);
        let b = parseInt(document.getElementById("bVal").value);
        if(!isNaN(r) && !isNaN(g) && !isNaN(b) && r>=0 && r<=255 && g>=0 && g<=255 && b>=0 && b<=255) {
            document.getElementById("customPreview").style.backgroundColor = `rgb(${r}, ${g}, ${b})`;
            const hex = "#" + ((1 << 24) + (r << 16) + (g << 8) + b).toString(16).slice(1);
            document.getElementById("hexVal").value = hex.toUpperCase();
        }
    }
    
    document.getElementById("rVal").addEventListener("input", updatePreviewFromRGB);
    document.getElementById("gVal").addEventListener("input", updatePreviewFromRGB);
    document.getElementById("bVal").addEventListener("input", updatePreviewFromRGB);
    document.getElementById("applyCustomBtn").onclick = applyCustomColor;
    
    document.getElementById("newMessageBtn").onclick = () => {
        if(!canPostMessage()) { alert("Hari ini sudah 3 pesan. Besok lagi! 🌱"); return; }
        document.getElementById("authorName").value = "";
        document.getElementById("messageInput").value = "";
        document.getElementById("charCountNow").innerText = "0";
        document.getElementById("createModal").classList.add("active");
        pendingMessageData = null;
        // reset custom preview
        document.getElementById("customPreview").style.backgroundColor = "#c7e9b0";
    };
    document.getElementById("pickLocationBtn").onclick = () => {
        const txt = document.getElementById("messageInput").value.trim();
        const author = document.getElementById("authorName").value.trim();
        if(txt === "") { alert("Pesan tidak boleh kosong!"); return; }
        if(txt.length > 500) { alert("Maksimal 500 karakter!"); return; }
        pendingMessageData = {
            text: txt,
            author: author === "" ? "Anonim" : author,
            color: selectedColorVal
        };
        document.getElementById("createModal").classList.remove("active");
        startPositionSelection();
    };
    document.getElementById("cancelCreateBtn").onclick = () => {
        document.getElementById("createModal").classList.remove("active");
        if(isSelectingPosition) { isSelectingPosition = false; treeWrapper.style.cursor = "default"; }
    };
    document.getElementById("messageInput").addEventListener("input", (e) => {
        document.getElementById("charCountNow").innerText = e.target.value.length;
    });
    document.getElementById("refreshBtn").onclick = () => { renderSmallCards(); };
    
    function createClouds() {
        for(let i=0;i<7;i++) {
            const cloud = document.createElement("div");
            cloud.classList.add("cloud");
            const w = 70 + Math.random() * 100;
            cloud.style.width = w + "px";
            cloud.style.height = (w * 0.45) + "px";
            cloud.style.top = (20 + Math.random() * 220) + "px";
            cloud.style.animationDuration = (18 + Math.random() * 45) + "s";
            cloud.style.animationDelay = (Math.random() * 20) + "s";
            cloud.style.background = "rgba(255, 250, 230, 0.95)";
            document.querySelector(".sky").appendChild(cloud);
        }
    }
    
    loadMessages();
    updateDailyLimit();
    buildColorGrid();
    createClouds();
    
    setInterval(() => {
        const nowDate = new Date().toISOString().slice(0,10);
        if(nowDate !== todayStr) { todayStr = nowDate; updateDailyLimit(); }
    }, 60000);
</script>
</body>
</html>
