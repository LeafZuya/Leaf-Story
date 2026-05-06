<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Leaf-Story | Perpus Cerita Hijau-Biru</title>
    <!-- Google Fonts & Font Awesome -->
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
            background: linear-gradient(135deg, #e0f2e9 0%, #b8dfd0 100%);
            color: #1a3f2c;
            min-height: 100vh;
        }

        /* ========== TAMPILAN HALAMAN UTAMA (BERANDA) ========== */
        .container-home {
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
            backdrop-filter: blur(10px);
            padding: 0.7rem 2rem;
            border-radius: 60px;
            margin-bottom: 2rem;
            box-shadow: 0 6px 18px rgba(30, 70, 50, 0.1);
            border: 1px solid rgba(70, 130, 90, 0.3);
        }

        .logo h1 {
            font-family: 'Playfair Display', serif;
            font-size: 1.9rem;
            background: linear-gradient(125deg, #146c42, #0b8a57);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
        }
        .logo p { font-size: 0.7rem; color: #2b6e48; }

        .nav-links a {
            margin-left: 1.5rem;
            text-decoration: none;
            font-weight: 500;
            color: #1a5a39;
            transition: 0.2s;
        }
        .nav-links a i { margin-right: 6px; }
        .nav-links a:hover { color: #0c6b3c; border-bottom: 2px solid #2e8b57; }

        .hero {
            background: linear-gradient(115deg, #cbe6db, #b7ddcb);
            border-radius: 48px;
            padding: 2rem 2.5rem;
            margin-bottom: 2.5rem;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
        }
        .hero-text h2 { font-size: 2rem; font-family: 'Playfair Display', serif; color: #115f35; }
        .btn-primary {
            background: #1f7a4a;
            color: white;
            border: none;
            padding: 0.7rem 1.6rem;
            border-radius: 36px;
            font-weight: 600;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: 0.2s;
        }
        .btn-primary:hover { background: #0f633b; transform: translateY(-3px); }

        .section-title {
            font-family: 'Playfair Display', serif;
            margin: 2rem 0 1rem;
            font-size: 1.8rem;
            color: #1e5e39;
            border-left: 6px solid #2a9d6e;
            padding-left: 1rem;
        }

        /* Form Upload */
        .upload-card {
            background: rgba(255, 255, 245, 0.95);
            border-radius: 32px;
            padding: 1.8rem;
            margin-bottom: 2rem;
            box-shadow: 0 10px 22px rgba(0,0,0,0.05);
            border: 1px solid #bbdbc9;
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
            padding: 10px 12px;
            border-radius: 28px;
            border: 1px solid #bfdecb;
            background: #fefef7;
            font-family: 'Inter', sans-serif;
            outline: none;
        }
        .color-row { display: flex; align-items: center; gap: 10px; }
        .color-row input[type="color"] { width: 55px; height: 45px; border-radius: 20px; }
        .tag-multiselect {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-top: 8px;
            max-height: 130px;
            overflow-y: auto;
            padding: 6px;
            background: #faf9ef;
            border-radius: 28px;
        }
        .tag-option-multi {
            background: #e0f0e8;
            padding: 5px 12px;
            border-radius: 30px;
            font-size: 0.75rem;
            cursor: pointer;
            transition: 0.1s;
        }
        .tag-option-multi.selected { background: #2a9d6e; color: white; }
        .file-info { font-size: 0.7rem; color: #4c7b63; margin-top: 5px; }

        /* Grid Card */
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
            box-shadow: 0 12px 20px -12px rgba(0, 0, 0, 0.2);
            display: flex;
            flex-direction: column;
        }
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
        .card-title { font-family: 'Playfair Display', serif; font-size: 1.4rem; font-weight: 700; }
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
            font-size: 0.85rem;
        }
        .btn-read-large:hover { background: #1f6e46; transform: scale(1.02); }
        .empty-message { text-align: center; padding: 3rem; background: #e2f0e9; border-radius: 48px; color: #2f6a48; }

        footer { text-align: center; margin-top: 3rem; padding: 1.5rem; color: #327a54; }

        /* ========== HALAMAN BACA (DESAIN EKSKLUSIF HIJAU-BIRU ES) ========== */
        .read-page-container {
            max-width: 1000px;
            margin: 2rem auto;
            padding: 0 1.5rem;
        }

        /* Kotak putih dengan bayangan, background gradien es */
        .story-card {
            background: linear-gradient(145deg, #ffffff, #f0faf5);
            border-radius: 48px;
            box-shadow: 0 20px 40px rgba(0, 30, 20, 0.2);
            overflow: hidden;
            border: 1px solid rgba(46, 139, 86, 0.3);
        }

        /* Header hijau daun di halaman baca */
        .story-header {
            background: linear-gradient(115deg, #1e784c, #259b60);
            padding: 2rem;
            text-align: center;
            color: white;
        }
        .story-header h1 {
            font-family: 'Playfair Display', serif;
            font-size: 2.4rem;
            margin-bottom: 0.5rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }

        /* Garis bawah pemisah */
        .separator {
            width: 80px;
            height: 4px;
            background: #ffd966;
            margin: 1rem auto 0;
            border-radius: 4px;
        }

        /* Area info (deskripsi di kotak samping kanan atas + author RGB) */
        .info-panel {
            display: flex;
            flex-wrap: wrap;
            gap: 1.8rem;
            padding: 1.8rem 2rem;
            background: #e7f3ef;
            border-bottom: 2px dashed #9ac9b0;
        }
        .desc-box {
            flex: 2;
            background: #ffffffcc;
            backdrop-filter: blur(4px);
            padding: 1rem 1.4rem;
            border-radius: 28px;
            border: 1px solid #7bb894;
            box-shadow: 0 6px 12px rgba(0,0,0,0.05);
        }
        .desc-box h3 {
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            color: #1d6b42;
            margin-bottom: 6px;
        }
        .desc-box p {
            color: #2c5a42;
            line-height: 1.5;
        }
        .meta-side {
            flex: 1;
            background: #d9eee4;
            border-radius: 28px;
            padding: 1rem;
            text-align: center;
            box-shadow: 0 4px 8px rgba(0,0,0,0.05);
        }
        .meta-side .tag-group {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 6px;
            margin: 12px 0;
        }
        /* Nama author dengan efek RGB */
        .author-rgb {
            font-size: 1.4rem;
            font-weight: 700;
            background: linear-gradient(90deg, #ff0066, #00ffff, #ffcc00);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            animation: rgbShift 3s infinite;
            display: inline-block;
        }
        @keyframes rgbShift {
            0% { filter: hue-rotate(0deg); }
            100% { filter: hue-rotate(360deg); }
        }

        /* Kotak garis mengelilingi isi story */
        .story-content-wrapper {
            margin: 2rem;
            border: 3px solid #2a9d6e;
            border-radius: 32px;
            background: #fffef7;
            padding: 1.5rem;
            box-shadow: inset 0 0 0 1px #cbe6db, 0 10px 20px rgba(0,0,0,0.05);
        }
        .story-content-inner {
            font-family: 'Inter', serif;
            line-height: 1.75;
            font-size: 1rem;
            white-space: pre-wrap;
        }
        .story-content-inner p { margin-bottom: 1rem; }
        .story-content-inner .dialogue {
            background: #eef6f0;
            border-left: 5px solid #2e8b57;
            padding: 0.3rem 1rem;
            margin: 0.8rem 0;
            border-radius: 16px;
            font-style: normal;
        }
        .story-content-inner strong { font-weight: 700; color: #195f3a; }
        .story-content-inner em { font-style: italic; color: #2e6d49; }

        /* Tombol kembali berwarna merah di paling bawah */
        .back-home-red {
            display: flex;
            justify-content: center;
            margin: 2rem 0 3rem;
        }
        .btn-red-home {
            background: #dc3545;
            color: white;
            border: none;
            padding: 12px 32px;
            border-radius: 60px;
            font-weight: bold;
            font-size: 1.1rem;
            cursor: pointer;
            transition: 0.2s;
            display: inline-flex;
            align-items: center;
            gap: 12px;
            box-shadow: 0 5px 12px rgba(0,0,0,0.2);
        }
        .btn-red-home:hover {
            background: #b02a37;
            transform: scale(1.02);
            box-shadow: 0 8px 18px rgba(0,0,0,0.2);
        }

        @media (max-width: 700px) {
            .container-home { padding: 1rem; }
            .navbar { flex-direction: column; }
            .info-panel { flex-direction: column; }
            .story-header h1 { font-size: 1.8rem; }
        }
    </style>
</head>
<body id="app-root">
    <!-- Tempat konten akan di-render secara dinamis -->
</body>

<script>
    // ======================== DATA & STORAGE (ONLINE / SHARED) ========================
    const ALL_TAGS = [
        "Fantasi", "Sci-fi", "Misteri", "Romantis", "Petualangan", "Horor", "Sejarah", "Legenda", 
        "Mythologie", "Slice of Life", "Storytelling", "Drama", "Komedi", "Thriller", "Psikologis",
        "Spiritual", "Young Adult", "Distopia", "Detektif", "Pernikahan", "Klasik", "Metropop", "Action"
    ];
    
    let stories = [];
    
    function loadStories() {
        const stored = localStorage.getItem("leafStory_onlineCollection");
        if(stored) stories = JSON.parse(stored);
        else stories = [];
    }
    function saveStories() {
        localStorage.setItem("leafStory_onlineCollection", JSON.stringify(stories));
    }
    
    // Helper escape
    function escapeHtml(str) { if(!str) return ''; return str.replace(/[&<>]/g, m => m === '&' ? '&amp;' : (m === '<' ? '&lt;' : '&gt;')); }
    
    // Parsing markdown: *italic* , **bold** , "dialog"
    function parseMarkdown(text) {
        if(!text) return "";
        let safe = text.replace(/[&<>]/g, m => m === '&' ? '&amp;' : (m === '<' ? '&lt;' : '&gt;'));
        safe = safe.replace(/\*\*(.+?)\*\*/gs, '<strong>$1</strong>');
        safe = safe.replace(/\*(.+?)\*/gs, '<em>$1</em>');
        safe = safe.replace(/"([^"]+)"/g, '<span class="dialogue">“$1”</span>');
        let paragraphs = safe.split(/\n\s*\n/);
        let parsed = paragraphs.map(p => {
            if(p.trim() === "") return "";
            let lineBreaks = p.replace(/\n/g, '<br>');
            return `<p>${lineBreaks}</p>`;
        }).join('');
        return parsed || `<p>${safe.replace(/\n/g, '<br>')}</p>`;
    }
    
    // ======================== HALAMAN UTAMA (BERANDA) ========================
    function renderHomepage() {
        const root = document.getElementById("app-root");
        root.innerHTML = `
            <div class="container-home">
                <div class="navbar">
                    <div class="logo"><h1><i class="fas fa-leaf"></i> Leaf-Story</h1><p>cerita online | *miring* **tebal** "dialog"</p></div>
                    <div class="nav-links">
                        <a href="#" id="homeRefreshLink"><i class="fas fa-home"></i> Beranda</a>
                        <a href="#uploadSection"><i class="fas fa-cloud-upload-alt"></i> Unggah Cerita</a>
                        <a href="#koleksiSection"><i class="fas fa-book"></i> Semua Cerita</a>
                    </div>
                </div>
                <div class="hero">
                    <div class="hero-text">
                        <h2>Perpus cerita bersama 🌿</h2>
                        <p>Upload ceritamu → langsung bisa dibaca siapa pun di sini. Setiap cerita punya halaman baca eksklusif!</p>
                        <button class="btn-primary" id="scrollToUploadBtn"><i class="fas fa-feather-alt"></i> Tulis & Unggah</button>
                    </div>
                    <div style="font-size: 3rem;">📚💙</div>
                </div>
                <div id="uploadSection">
                    <h2 class="section-title"><i class="fas fa-pen-fancy"></i> Tambah Cerita Baru</h2>
                    <div class="upload-card">
                        <div class="form-grid">
                            <div class="form-group"><label>Judul Novel</label><input type="text" id="novelTitle" placeholder="Misal: Kristal Es di Hutan"></div>
                            <div class="form-group"><label>Nama Author</label><input type="text" id="novelAuthor" placeholder="Nama pena"></div>
                            <div class="form-group">
                                <label>Pilih Tag (bisa banyak)</label>
                                <div class="tag-multiselect" id="tagMultiselectContainer"></div>
                            </div>
                            <div class="form-group"><label>Deskripsi Singkat (Card)</label><textarea rows="2" id="novelDesc" placeholder="Cuplikan cerita..."></textarea></div>
                            <div class="form-group"><label>Warna Card (Header)</label><div class="color-row"><input type="color" id="cardColor" value="#2b7a4b"><span>pilih warna</span></div></div>
                            <div class="form-group"><label>Upload File Novel (TXT/MD)</label><input type="file" id="novelFile" accept=".txt,.md,.text/plain"><div class="file-info"><i class="fas fa-info-circle"></i> File teks, maks 100MB. Support *italic* , **bold** , "dialog"</div></div>
                        </div>
                        <div style="margin-top:1.5rem; display:flex; justify-content:flex-end;"><button class="btn-primary" id="publishStoryBtn"><i class="fas fa-globe"></i> Terbitkan (Online)</button></div>
                    </div>
                </div>
                <div id="koleksiSection">
                    <h2 class="section-title"><i class="fas fa-tree"></i> Koleksi Cerita (Semua Pengguna)</h2>
                    <div id="novelGridContainer" class="novel-grid"></div>
                </div>
                <footer><i class="fas fa-seedling"></i> Leaf-Story — cerita tersimpan online di perangkat ini. Setiap cerita punya halaman baca spesial.</footer>
            </div>
        `;
        // Render tag selector
        const tagContainer = document.getElementById("tagMultiselectContainer");
        if(tagContainer) {
            tagContainer.innerHTML = "";
            ALL_TAGS.forEach(tag => {
                const span = document.createElement("span");
                span.classList.add("tag-option-multi");
                span.innerText = tag;
                span.setAttribute("data-tagval", tag);
                span.addEventListener("click", () => span.classList.toggle("selected"));
                tagContainer.appendChild(span);
            });
        }
        // Muat stories dan render card
        loadStories();
        renderAllCards();
        // Event listeners
        document.getElementById("publishStoryBtn")?.addEventListener("click", publishStory);
        document.getElementById("scrollToUploadBtn")?.addEventListener("click", () => document.getElementById("uploadSection").scrollIntoView({ behavior: "smooth" }));
        document.getElementById("homeRefreshLink")?.addEventListener("click", (e) => { e.preventDefault(); window.location.href = "/"; });
    }
    
    function getSelectedTagsFromForm() {
        const selectedSpans = document.querySelectorAll("#tagMultiselectContainer .tag-option-multi.selected");
        return Array.from(selectedSpans).map(s => s.getAttribute("data-tagval"));
    }
    
    async function publishStory() {
        const title = document.getElementById("novelTitle").value.trim();
        const author = document.getElementById("novelAuthor").value.trim();
        const description = document.getElementById("novelDesc").value.trim();
        const cardColor = document.getElementById("cardColor").value;
        const selectedTags = getSelectedTagsFromForm();
        const fileInput = document.getElementById("novelFile");
        const file = fileInput.files[0];
        if(!title || !author) { alert("Judul dan Author harus diisi!"); return; }
        if(selectedTags.length === 0) { alert("Pilih minimal 1 tag!"); return; }
        if(!file) { alert("Upload file .txt atau .md"); return; }
        if(file.size > 100 * 1024 * 1024) { alert("File maks 100MB"); return; }
        let fileContent = "";
        try {
            const reader = new FileReader();
            fileContent = await new Promise((resolve, reject) => {
                reader.onload = e => resolve(e.target.result);
                reader.onerror = () => reject("Gagal baca file");
                reader.readAsText(file, "UTF-8");
            });
        } catch(err) { alert(`Error: ${err}`); return; }
        
        const newStory = {
            id: Date.now(),
            title, author,
            tags: selectedTags,
            description: description || "Tidak ada deskripsi",
            cardColor: cardColor,
            createdAt: new Date().toISOString(),
            fileContent: fileContent.slice(0, 1000000)
        };
        stories.unshift(newStory);
        saveStories();
        // Reset form
        document.getElementById("novelTitle").value = "";
        document.getElementById("novelAuthor").value = "";
        document.getElementById("novelDesc").value = "";
        document.getElementById("cardColor").value = "#2b7a4b";
        document.querySelectorAll("#tagMultiselectContainer .tag-option-multi.selected").forEach(t => t.classList.remove("selected"));
        document.getElementById("novelFile").value = "";
        alert(`✨ "${title}" berhasil diterbitkan! Semua pengunjung bisa membaca.`);
        renderAllCards();
        document.getElementById("koleksiSection").scrollIntoView({ behavior: "smooth" });
    }
    
    function renderAllCards() {
        const container = document.getElementById("novelGridContainer");
        if(!stories.length) {
            container.innerHTML = `<div class="empty-message"><i class="fas fa-leaf fa-2x"></i><p>Belum ada cerita. Jadilah yang pertama!</p></div>`;
            return;
        }
        container.innerHTML = stories.map(story => {
            const headerStyle = `background: ${story.cardColor || "#2b7a4b"};`;
            const tagChips = (story.tags || []).slice(0, 3).map(t => `<span class="mini-tag">${escapeHtml(t)}</span>`).join('');
            const moreTag = (story.tags.length > 3) ? `<span class="mini-tag">+${story.tags.length-3}</span>` : '';
            return `
                <div class="novel-card" data-id="${story.id}">
                    <div class="card-header" style="${headerStyle}"><i class="fas fa-book-open"></i><span>✨ cerita</span></div>
                    <div class="card-content">
                        <div class="card-title">${escapeHtml(story.title)}</div>
                        <div>oleh ${escapeHtml(story.author)}</div>
                        <div class="tag-list">${tagChips} ${moreTag}</div>
                        <div class="card-desc">${escapeHtml(story.description.substring(0,110))}${story.description.length>110?'...':''}</div>
                        <div class="card-meta">
                            <span><i class="far fa-calendar-alt"></i> ${new Date(story.createdAt).toLocaleDateString()}</span>
                            <button class="btn-read-large" data-read-id="${story.id}"><i class="fas fa-book-reader"></i> Baca Sekarang</button>
                        </div>
                    </div>
                </div>
            `;
        }).join('');
        document.querySelectorAll('.btn-read-large').forEach(btn => {
            btn.addEventListener('click', (e) => {
                e.stopPropagation();
                const id = btn.getAttribute('data-read-id');
                if(id) window.location.href = `?read=${id}`;
            });
        });
    }
    
    // ======================== HALAMAN BACA (DENGAN DESAIN CANTIK) ========================
    function renderReadPage(storyId) {
        const story = stories.find(s => s.id == storyId);
        if(!story) {
            document.getElementById("app-root").innerHTML = `<div style="text-align:center;margin-top:4rem;"><h2>Cerita tidak ditemukan</h2><button onclick="window.location.href='/'">Kembali ke Beranda</button></div>`;
            return;
        }
        const parsedContent = parseMarkdown(story.fileContent || "Konten tidak tersedia.");
        const tagHtml = (story.tags || []).map(t => `<span class="mini-tag">${escapeHtml(t)}</span>`).join('');
        const html = `
            <div class="read-page-container">
                <div class="story-card">
                    <div class="story-header">
                        <h1>${escapeHtml(story.title)}</h1>
                        <div class="separator"></div>
                    </div>
                    <div class="info-panel">
                        <div class="desc-box">
                            <h3><i class="fas fa-quote-left"></i> Sinopsis</h3>
                            <p>${escapeHtml(story.description || "Tidak ada deskripsi")}</p>
                        </div>
                        <div class="meta-side">
                            <div><i class="fas fa-tags"></i> Tema</div>
                            <div class="tag-group">${tagHtml}</div>
                            <div style="margin-top: 12px;">
                                <span class="author-rgb"><i class="fas fa-user-astronaut"></i> ${escapeHtml(story.author)}</span>
                            </div>
                            <div style="font-size:0.7rem; margin-top:8px;"><i class="far fa-calendar"></i> ${new Date(story.createdAt).toLocaleDateString()}</div>
                        </div>
                    </div>
                    <div class="story-content-wrapper">
                        <div class="story-content-inner">
                            ${parsedContent}
                        </div>
                    </div>
                    <div class="back-home-red">
                        <button id="backToHomeRedBtn" class="btn-red-home"><i class="fas fa-home"></i> Kembali ke Beranda</button>
                    </div>
                </div>
            </div>
        `;
        document.getElementById("app-root").innerHTML = html;
        const backBtn = document.getElementById("backToHomeRedBtn");
        if(backBtn) backBtn.addEventListener("click", () => { window.location.href = "/"; });
    }
    
    // ======================== ROUTING PASTI TIDAK 404 ========================
    function route() {
        const params = new URLSearchParams(window.location.search);
        const readId = params.get('read');
        loadStories(); // selalu load terbaru dari storage
        if(readId) {
            renderReadPage(readId);
        } else {
            renderHomepage();
        }
    }
    
    // Jalankan routing
    route();
</script>
</html>
