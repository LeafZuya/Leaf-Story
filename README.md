<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Leaf-Story | Taman Cerita Hijau Biru</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;400;500;600;700&family=Playfair+Display:ital,wght@0,400;0,500;0,600;1,400&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: linear-gradient(135deg, #d4efe4 0%, #b5dfce 100%);
            min-height: 100vh;
            color: #1a3f2c;
        }

        /* ========== TAMPILAN HALAMAN UTAMA ========== */
        .home-container {
            max-width: 1300px;
            margin: 0 auto;
            padding: 1.5rem 2rem;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(12px);
            padding: 0.7rem 2rem;
            border-radius: 80px;
            margin-bottom: 2rem;
            box-shadow: 0 8px 25px rgba(30, 70, 50, 0.15);
            border: 1px solid rgba(70, 140, 100, 0.4);
        }

        .logo h1 {
            font-family: 'Playfair Display', serif;
            font-size: 2rem;
            background: linear-gradient(135deg, #0f6e41, #0c9b60);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
        }
        .logo p { font-size: 0.7rem; color: #2b6e48; letter-spacing: 1px; }

        .nav-links a {
            margin-left: 1.5rem;
            text-decoration: none;
            font-weight: 600;
            color: #1a5a39;
            transition: 0.2s;
        }
        .nav-links a i { margin-right: 6px; }
        .nav-links a:hover { color: #0e874c; border-bottom: 2px solid #2e8b57; }

        .hero {
            background: linear-gradient(125deg, #c2e0d3, #a6d4bf);
            border-radius: 48px;
            padding: 2.5rem;
            margin-bottom: 2.5rem;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 12px 25px rgba(0,0,0,0.08);
        }
        .hero-text h2 { font-size: 2.2rem; font-family: 'Playfair Display', serif; color: #0b5432; }
        .hero-text p { margin: 0.8rem 0; color: #255e40; }
        .btn-primary {
            background: #1f7a4a;
            color: white;
            border: none;
            padding: 0.75rem 1.8rem;
            border-radius: 40px;
            font-weight: 600;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: 0.2s;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }
        .btn-primary:hover { background: #0f633b; transform: translateY(-3px); }

        .section-title {
            font-family: 'Playfair Display', serif;
            margin: 2rem 0 1rem;
            font-size: 1.8rem;
            color: #1e6b41;
            border-left: 6px solid #2a9d6e;
            padding-left: 1rem;
        }

        .upload-card {
            background: rgba(255, 255, 250, 0.95);
            border-radius: 36px;
            padding: 1.8rem;
            margin-bottom: 2rem;
            box-shadow: 0 12px 28px rgba(0,0,0,0.08);
            border: 1px solid #b8ddca;
        }
        .form-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 1.2rem;
            margin-top: 1rem;
        }
        .form-group { flex: 1; min-width: 200px; }
        .form-group label { font-weight: 600; display: block; margin-bottom: 6px; color: #1b6b42; }
        input, textarea {
            width: 100%;
            padding: 10px 14px;
            border-radius: 30px;
            border: 1px solid #c2e0d0;
            background: #ffffff;
            font-family: 'Inter', sans-serif;
            outline: none;
        }
        input:focus, textarea:focus { border-color: #2c8b58; box-shadow: 0 0 0 3px rgba(44,139,88,0.2); }
        .color-row { display: flex; align-items: center; gap: 10px; }
        .color-row input[type="color"] { width: 55px; height: 45px; border-radius: 20px; }
        .tag-multiselect {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-top: 8px;
            max-height: 130px;
            overflow-y: auto;
            padding: 8px;
            background: #f8fcf5;
            border-radius: 28px;
            border: 1px solid #cde2d6;
        }
        .tag-option-multi {
            background: #e3f1ea;
            padding: 5px 14px;
            border-radius: 40px;
            font-size: 0.75rem;
            cursor: pointer;
            transition: 0.1s;
        }
        .tag-option-multi.selected { background: #2a9d6e; color: white; }
        .file-info { font-size: 0.7rem; color: #4c7b63; margin-top: 5px; }

        .novel-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(340px, 1fr));
            gap: 2rem;
            margin: 2rem 0;
        }
        .novel-card {
            background: white;
            border-radius: 32px;
            overflow: hidden;
            transition: 0.25s ease;
            box-shadow: 0 15px 25px -12px rgba(0, 0, 0, 0.2);
            display: flex;
            flex-direction: column;
        }
        .novel-card:hover { transform: translateY(-6px); box-shadow: 0 22px 30px -12px #1a4d2e80; }
        .card-header {
            height: 120px;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            color: white;
            text-shadow: 1px 1px 3px rgba(0,0,0,0.3);
        }
        .card-header i { font-size: 2.6rem; margin-bottom: 6px; }
        .card-content { padding: 1.3rem; flex-grow: 1; }
        .card-title { font-family: 'Playfair Display', serif; font-size: 1.4rem; font-weight: 700; color: #135a33; }
        .tag-list { display: flex; flex-wrap: wrap; gap: 6px; margin: 10px 0; }
        .mini-tag { background: #e2f0ea; border-radius: 30px; font-size: 0.65rem; padding: 3px 10px; }
        .card-desc { font-size: 0.85rem; color: #336b4d; margin: 8px 0; display: -webkit-box; -webkit-line-clamp: 3; -webkit-box-orient: vertical; overflow: hidden; }
        .card-meta { display: flex; justify-content: space-between; align-items: center; margin-top: 1rem; border-top: 1px solid #cde0d4; padding-top: 0.8rem; }
        .btn-read-large {
            background: #2e8b57;
            color: white;
            border: none;
            padding: 8px 20px;
            border-radius: 40px;
            font-weight: bold;
            cursor: pointer;
            transition: 0.2s;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }
        .btn-read-large:hover { background: #1f6e46; transform: scale(1.02); }
        .empty-message { text-align: center; padding: 3rem; background: #e2f0e9; border-radius: 48px; color: #2f6a48; }

        footer { text-align: center; margin-top: 3rem; padding: 1.5rem; color: #2d6b4a; border-top: 1px solid #b9dac9; }

        /* ========== HALAMAN BACA (HIJAU BIRU ES + KOTAK GARIS) ========== */
        .read-wrapper {
            max-width: 1000px;
            margin: 2rem auto;
            padding: 0 1.5rem;
        }
        .read-card {
            background: linear-gradient(145deg, #ffffff, #f3fdf8);
            border-radius: 56px;
            box-shadow: 0 25px 45px rgba(0, 40, 20, 0.25);
            overflow: hidden;
            border: 1px solid rgba(70, 150, 100, 0.4);
        }
        .read-header {
            background: linear-gradient(115deg, #1a6e46, #289f66);
            padding: 2rem;
            text-align: center;
            color: white;
        }
        .read-header h1 {
            font-family: 'Playfair Display', serif;
            font-size: 2.3rem;
            letter-spacing: -0.3px;
        }
        .header-separator {
            width: 90px;
            height: 4px;
            background: #ffdf80;
            margin: 0.8rem auto 0;
            border-radius: 4px;
        }
        /* Info panel dengan deskripsi di kotak kanan atas */
        .read-info-panel {
            display: flex;
            flex-wrap: wrap;
            gap: 1.5rem;
            padding: 1.8rem 2rem;
            background: #e2f3eb;
            border-bottom: 2px dashed #9bc2ab;
        }
        .desc-card {
            flex: 2;
            background: #ffffffdd;
            backdrop-filter: blur(4px);
            padding: 1rem 1.4rem;
            border-radius: 32px;
            border: 1px solid #7eb893;
            box-shadow: 0 5px 12px rgba(0,0,0,0.05);
        }
        .desc-card h3 { color: #1a683f; margin-bottom: 6px; font-size: 0.9rem; letter-spacing: 1px; }
        .side-meta {
            flex: 1;
            background: #cde9dd;
            border-radius: 32px;
            padding: 1rem;
            text-align: center;
        }
        .side-meta .tag-bunch { display: flex; flex-wrap: wrap; justify-content: center; gap: 6px; margin: 12px 0; }
        /* Author RGB animasi */
        .author-rgb-glow {
            font-size: 1.5rem;
            font-weight: 800;
            background: linear-gradient(90deg, #ff3366, #00e0ff, #ffcc33);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            animation: rgbFlow 2.5s infinite;
            display: inline-block;
        }
        @keyframes rgbFlow {
            0% { filter: hue-rotate(0deg); }
            100% { filter: hue-rotate(360deg); }
        }
        /* Kotak garis mengelilingi cerita */
        .story-border-box {
            margin: 2rem;
            border: 3px solid #2a9d6e;
            border-radius: 40px;
            background: #fffef5;
            padding: 1.8rem;
            box-shadow: inset 0 0 0 2px #e0f3e8, 0 12px 18px rgba(0,0,0,0.05);
        }
        .story-text-content {
            font-family: 'Inter', serif;
            line-height: 1.75;
            font-size: 1rem;
            white-space: pre-wrap;
        }
        .story-text-content p { margin-bottom: 1rem; }
        .story-text-content .dialogue {
            background: #eef6f0;
            border-left: 5px solid #2e8b57;
            padding: 0.3rem 1rem;
            margin: 0.8rem 0;
            border-radius: 20px;
            font-style: normal;
        }
        .story-text-content strong { color: #1a7044; font-weight: 700; }
        .story-text-content em { color: #2f6e4a; font-style: italic; }
        /* Tombol merah kembali di bawah */
        .red-back-btn {
            display: flex;
            justify-content: center;
            margin: 2rem 0 2.5rem;
        }
        .btn-red-home {
            background: #dc3545;
            color: white;
            border: none;
            padding: 12px 36px;
            border-radius: 60px;
            font-weight: bold;
            font-size: 1.05rem;
            cursor: pointer;
            box-shadow: 0 5px 14px rgba(0,0,0,0.2);
            transition: 0.2s;
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }
        .btn-red-home:hover { background: #b52b3a; transform: scale(1.02); }

        @media (max-width: 700px) {
            .home-container { padding: 1rem; }
            .navbar { flex-direction: column; }
            .read-info-panel { flex-direction: column; }
            .story-border-box { margin: 1rem; }
        }
    </style>
</head>
<body id="app"></body>

<script>
    // ======================== STORAGE & DATA ========================
    const TAG_LIST = [
        "Fantasi", "Sci-fi", "Misteri", "Romantis", "Petualangan", "Horor", "Sejarah", "Legenda", 
        "Mythologie", "Slice of Life", "Storytelling", "Drama", "Komedi", "Thriller", "Psikologis",
        "Spiritual", "Young Adult", "Distopia", "Detektif", "Pernikahan", "Klasik", "Metropop", "Action", "Pedih"
    ];
    
    let globalStories = [];
    
    function loadStores() {
        const raw = localStorage.getItem("leafStory_hijauBiru");
        if(raw) globalStories = JSON.parse(raw);
        else globalStories = [];
    }
    function saveStores() {
        localStorage.setItem("leafStory_hijauBiru", JSON.stringify(globalStories));
    }
    
    function escapeHtml(str) { if(!str) return ''; return str.replace(/[&<>]/g, m => m === '&' ? '&amp;' : (m === '<' ? '&lt;' : '&gt;')); }
    
    // parser markdown: *italic* , **bold** , "dialog"
    function parseMarkdown(text) {
        if(!text) return "";
        let safe = text.replace(/[&<>]/g, m => m === '&' ? '&amp;' : (m === '<' ? '&lt;' : '&gt;'));
        safe = safe.replace(/\*\*(.+?)\*\*/gs, '<strong>$1</strong>');
        safe = safe.replace(/\*(.+?)\*/gs, '<em>$1</em>');
        safe = safe.replace(/"([^"]+)"/g, '<span class="dialogue">“$1”</span>');
        let paras = safe.split(/\n\s*\n/);
        let result = paras.map(p => {
            if(p.trim() === "") return "";
            return `<p>${p.replace(/\n/g, '<br>')}</p>`;
        }).join('');
        return result || `<p>${safe.replace(/\n/g, '<br>')}</p>`;
    }
    
    // ======================== RENDER HALAMAN UTAMA ========================
    function renderHome() {
        const app = document.getElementById("app");
        app.innerHTML = `
            <div class="home-container">
                <div class="navbar">
                    <div class="logo"><h1><i class="fas fa-leaf"></i> Leaf-Story</h1><p>cerita online | *miring* **tebal** "dialog"</p></div>
                    <div class="nav-links">
                        <a href="#" id="refreshHome"><i class="fas fa-home"></i> Beranda</a>
                        <a href="#uploadArea"><i class="fas fa-cloud-upload-alt"></i> Unggah Cerita</a>
                        <a href="#koleksiArea"><i class="fas fa-book"></i> Koleksi</a>
                    </div>
                </div>
                <div class="hero">
                    <div class="hero-text">
                        <h2>🌿 Daun cerita, langit biru</h2>
                        <p>Upload novelmu, dan semua orang bisa membaca dengan halaman istimewa. Banyak tag, warna card, dan tampilan baca yang memukau.</p>
                        <button class="btn-primary" id="uploadScrollBtn"><i class="fas fa-feather-alt"></i> Bagikan Kisahmu</button>
                    </div>
                    <div><i class="fas fa-book-open" style="font-size: 4rem; color:#1d6b42;"></i></div>
                </div>
                <div id="uploadArea">
                    <h2 class="section-title"><i class="fas fa-pen-fancy"></i> Terbitkan Cerita Baru</h2>
                    <div class="upload-card">
                        <div class="form-grid">
                            <div class="form-group"><label>Judul Novel</label><input type="text" id="titleInput" placeholder="Mis: Kabut di Telaga Biru"></div>
                            <div class="form-group"><label>Nama Author</label><input type="text" id="authorInput" placeholder="Nama pena"></div>
                            <div class="form-group">
                                <label>Pilih Tag (bisa lebih dari satu)</label>
                                <div class="tag-multiselect" id="tagSelectArea"></div>
                            </div>
                            <div class="form-group"><label>Deskripsi Singkat</label><textarea rows="2" id="descInput" placeholder="Sinopsis singkat..."></textarea></div>
                            <div class="form-group"><label>Warna Card (Header)</label><div class="color-row"><input type="color" id="colorPicker" value="#2b7a4b"><span>pilih gradasi</span></div></div>
                            <div class="form-group"><label>Upload File Novel (TXT/MD)</label><input type="file" id="fileInput" accept=".txt,.md,.text/plain"><div class="file-info"><i class="fas fa-info-circle"></i> File teks, maks 100MB. Support *italic* , **bold** , "dialog"</div></div>
                        </div>
                        <div style="margin-top:1.5rem; display:flex; justify-content:flex-end;"><button class="btn-primary" id="publishBtn"><i class="fas fa-globe"></i> Terbitkan Sekarang</button></div>
                    </div>
                </div>
                <div id="koleksiArea">
                    <h2 class="section-title"><i class="fas fa-tree"></i> Koleksi Cerita (Semua Pengguna)</h2>
                    <div id="storyGrid" class="novel-grid"></div>
                </div>
                <footer><i class="fas fa-seedling"></i> Leaf-Story — cerita abadi dalam naungan hijau biru</footer>
            </div>
        `;
        
        // render tag multi select
        const tagContainer = document.getElementById("tagSelectArea");
        TAG_LIST.forEach(tag => {
            const span = document.createElement("span");
            span.className = "tag-option-multi";
            span.innerText = tag;
            span.setAttribute("data-val", tag);
            span.onclick = (e) => { e.stopPropagation(); span.classList.toggle("selected"); };
            tagContainer.appendChild(span);
        });
        
        loadStores();
        renderCards();
        
        document.getElementById("publishBtn").onclick = publishNewStory;
        document.getElementById("uploadScrollBtn").onclick = () => document.getElementById("uploadArea").scrollIntoView({ behavior: "smooth" });
        document.getElementById("refreshHome").onclick = (e) => { e.preventDefault(); window.location.href = "/"; };
    }
    
    function getSelectedTags() {
        const selected = document.querySelectorAll("#tagSelectArea .tag-option-multi.selected");
        return Array.from(selected).map(s => s.getAttribute("data-val"));
    }
    
    async function publishNewStory() {
        const title = document.getElementById("titleInput").value.trim();
        const author = document.getElementById("authorInput").value.trim();
        const desc = document.getElementById("descInput").value.trim();
        const color = document.getElementById("colorPicker").value;
        const tags = getSelectedTags();
        const file = document.getElementById("fileInput").files[0];
        if(!title || !author) { alert("Judul dan Author wajib diisi!"); return; }
        if(tags.length === 0) { alert("Pilih minimal satu tag!"); return; }
        if(!file) { alert("Upload file cerita (.txt/.md)"); return; }
        if(file.size > 100 * 1024 * 1024) { alert("Maksimal 100MB"); return; }
        let content = "";
        try {
            const reader = new FileReader();
            content = await new Promise((resolve, reject) => {
                reader.onload = e => resolve(e.target.result);
                reader.onerror = () => reject("Gagal membaca file");
                reader.readAsText(file, "UTF-8");
            });
        } catch(e) { alert("Error baca file"); return; }
        
        const newStory = {
            id: Date.now(),
            title, author, description: desc || "Tidak ada deskripsi",
            tags: tags, cardColor: color, createdAt: new Date().toISOString(),
            fileContent: content.slice(0, 1200000)
        };
        globalStories.unshift(newStory);
        saveStores();
        // reset form
        document.getElementById("titleInput").value = "";
        document.getElementById("authorInput").value = "";
        document.getElementById("descInput").value = "";
        document.getElementById("colorPicker").value = "#2b7a4b";
        document.querySelectorAll("#tagSelectArea .tag-option-multi.selected").forEach(t => t.classList.remove("selected"));
        document.getElementById("fileInput").value = "";
        alert(`✨ "${title}" berhasil diterbitkan! Koleksi terupdate.`);
        renderCards();
        document.getElementById("koleksiArea").scrollIntoView({ behavior: "smooth" });
    }
    
    function renderCards() {
        const grid = document.getElementById("storyGrid");
        if(!globalStories.length) {
            grid.innerHTML = `<div class="empty-message"><i class="fas fa-leaf fa-3x"></i><p style="margin-top:1rem;">Belum ada cerita, mulailah dengan mengunggah kisah pertamamu 🌱</p></div>`;
            return;
        }
        grid.innerHTML = globalStories.map(story => {
            const headerBg = story.cardColor || "#2b7a4b";
            const tagChips = story.tags.slice(0,3).map(t => `<span class="mini-tag">${escapeHtml(t)}</span>`).join('');
            const more = story.tags.length > 3 ? `<span class="mini-tag">+${story.tags.length-3}</span>` : '';
            return `
                <div class="novel-card">
                    <div class="card-header" style="background: ${headerBg};"><i class="fas fa-book-open"></i><span>📖 cerita</span></div>
                    <div class="card-content">
                        <div class="card-title">${escapeHtml(story.title)}</div>
                        <div>oleh ${escapeHtml(story.author)}</div>
                        <div class="tag-list">${tagChips} ${more}</div>
                        <div class="card-desc">${escapeHtml(story.description.substring(0,100))}${story.description.length>100?'...':''}</div>
                        <div class="card-meta">
                            <span><i class="far fa-calendar"></i> ${new Date(story.createdAt).toLocaleDateString()}</span>
                            <button class="btn-read-large" data-id="${story.id}"><i class="fas fa-book-reader"></i> Baca Sekarang</button>
                        </div>
                    </div>
                </div>
            `;
        }).join('');
        document.querySelectorAll(".btn-read-large").forEach(btn => {
            btn.onclick = (e) => {
                e.stopPropagation();
                const id = btn.getAttribute("data-id");
                if(id) window.location.href = `?read=${id}`;
            };
        });
    }
    
    // ======================== HALAMAN BACA (DENGAN DESAIN EKSKLUSIF) ========================
    function renderReadPage(storyId) {
        const story = globalStories.find(s => s.id == storyId);
        if(!story) {
            document.getElementById("app").innerHTML = `<div style="text-align:center; margin-top:4rem;"><h2>❌ Cerita tidak ditemukan</h2><button onclick="window.location.href='/'" style="background:#2e8b57; color:white; border:none; padding:10px 24px; border-radius:40px;">Kembali ke Beranda</button></div>`;
            return;
        }
        const parsedStory = parseMarkdown(story.fileContent || "Konten tidak tersedia.");
        const tagItems = story.tags.map(t => `<span class="mini-tag">${escapeHtml(t)}</span>`).join('');
        const html = `
            <div class="read-wrapper">
                <div class="read-card">
                    <div class="read-header">
                        <h1>${escapeHtml(story.title)}</h1>
                        <div class="header-separator"></div>
                    </div>
                    <div class="read-info-panel">
                        <div class="desc-card">
                            <h3><i class="fas fa-feather-alt"></i> Tentang Cerita</h3>
                            <p>${escapeHtml(story.description || "Tak ada deskripsi, biarkan imajinasi berbicara.")}</p>
                        </div>
                        <div class="side-meta">
                            <div><i class="fas fa-tags"></i> Label</div>
                            <div class="tag-bunch">${tagItems}</div>
                            <div style="margin-top: 8px;">
                                <span class="author-rgb-glow"><i class="fas fa-user-astronaut"></i> ${escapeHtml(story.author)}</span>
                            </div>
                            <div style="font-size:0.7rem; margin-top: 6px;"><i class="far fa-calendar-alt"></i> ${new Date(story.createdAt).toLocaleDateString()}</div>
                        </div>
                    </div>
                    <div class="story-border-box">
                        <div class="story-text-content">
                            ${parsedStory}
                        </div>
                    </div>
                    <div class="red-back-btn">
                        <button id="backHomeRedBtn" class="btn-red-home"><i class="fas fa-arrow-left"></i> Kembali ke Beranda</button>
                    </div>
                </div>
            </div>
        `;
        document.getElementById("app").innerHTML = html;
        document.getElementById("backHomeRedBtn").onclick = () => { window.location.href = "/"; };
    }
    
    // ======================== ROUTING AMAN TANPA 404 ========================
    function router() {
        loadStores();
        const params = new URLSearchParams(window.location.search);
        const readId = params.get("read");
        if(readId && globalStories.find(s => s.id == readId)) {
            renderReadPage(readId);
        } else if(readId && !globalStories.find(s => s.id == readId)) {
            // jika id tidak valid tetap kasih pesan
            document.getElementById("app").innerHTML = `<div style="text-align:center;margin:4rem"><h2>Cerita tidak tersedia</h2><button onclick="window.location.href='/'" style="background:#2e8b57; color:white; border:none; padding:10px 28px; border-radius:40px;">🏠 Beranda</button></div>`;
        } else {
            renderHome();
        }
    }
    
    router();
</script>
</html>
