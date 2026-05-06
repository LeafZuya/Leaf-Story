<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Leaf-Story | Perpus Cerita Bersama</title>
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
            background: linear-gradient(145deg, #eaf7f0 0%, #d0e6db 100%);
            font-family: 'Inter', sans-serif;
            color: #1a3f2c;
            scroll-behavior: smooth;
        }
        ::-webkit-scrollbar { width: 8px; }
        ::-webkit-scrollbar-track { background: #c2dbc9; border-radius: 10px; }
        ::-webkit-scrollbar-thumb { background: #2c7a4d; border-radius: 10px; }

        .container { max-width: 1300px; margin: 0 auto; padding: 1.5rem 2rem; }

        /* Navbar */
        .navbar {
            display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap;
            gap: 1rem; background: rgba(255, 255, 255, 0.8); backdrop-filter: blur(10px);
            padding: 0.7rem 2rem; border-radius: 60px; margin-bottom: 2rem;
            box-shadow: 0 6px 18px rgba(30, 70, 50, 0.1);
            border: 1px solid rgba(70, 130, 90, 0.3);
        }
        .logo h1 { font-family: 'Playfair Display', serif; font-size: 1.9rem; background: linear-gradient(125deg, #146c42, #0b8a57); background-clip: text; -webkit-background-clip: text; color: transparent; }
        .logo p { font-size: 0.7rem; color: #2b6e48; }
        .nav-links a { margin-left: 1.5rem; text-decoration: none; font-weight: 500; color: #1a5a39; transition: 0.2s; }
        .nav-links a i { margin-right: 6px; }
        .nav-links a:hover { color: #0c6b3c; border-bottom: 2px solid #2e8b57; }

        /* Hero */
        .hero {
            background: linear-gradient(115deg, #cbe6db, #b7ddcb);
            border-radius: 48px; padding: 2rem 2.5rem; margin-bottom: 2.5rem;
            display: flex; flex-wrap: wrap; justify-content: space-between; align-items: center;
        }
        .hero-text h2 { font-size: 2rem; font-family: 'Playfair Display', serif; color: #115f35; }
        .btn-primary { background: #1f7a4a; color: white; border: none; padding: 0.7rem 1.6rem; border-radius: 36px; font-weight: 600; cursor: pointer; display: inline-flex; align-items: center; gap: 8px; transition: 0.2s; }
        .btn-primary:hover { background: #0f633b; transform: translateY(-3px); }

        .section-title { font-family: 'Playfair Display', serif; margin: 2rem 0 1rem; font-size: 1.8rem; color: #1e5e39; border-left: 6px solid #2a9d6e; padding-left: 1rem; }

        /* Form Upload */
        .upload-card { background: rgba(255, 255, 245, 0.95); border-radius: 32px; padding: 1.8rem; margin-bottom: 2rem; box-shadow: 0 10px 22px rgba(0,0,0,0.05); border: 1px solid #bbdbc9; }
        .form-grid { display: flex; flex-wrap: wrap; gap: 1.2rem; margin-top: 1rem; }
        .form-group { flex: 1; min-width: 200px; }
        .form-group label { font-weight: 600; display: block; margin-bottom: 6px; color: #1b6b42; }
        input, select, textarea { width: 100%; padding: 10px 12px; border-radius: 28px; border: 1px solid #bfdecb; background: #fefef7; font-family: 'Inter', sans-serif; outline: none; }
        input:focus, textarea:focus { border-color: #2c8b58; box-shadow: 0 0 0 2px rgba(44,139,88,0.2); }
        .color-row { display: flex; align-items: center; gap: 10px; }
        .color-row input[type="color"] { width: 55px; height: 45px; border-radius: 20px; }
        .tag-multiselect { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 8px; max-height: 130px; overflow-y: auto; padding: 6px; background: #faf9ef; border-radius: 28px; }
        .tag-option-multi { background: #e0f0e8; padding: 5px 12px; border-radius: 30px; font-size: 0.75rem; cursor: pointer; transition: 0.1s; user-select: none; }
        .tag-option-multi.selected { background: #2a9d6e; color: white; box-shadow: 0 2px 6px rgba(0,0,0,0.1); }
        .file-info { font-size: 0.7rem; color: #4c7b63; margin-top: 5px; }

        /* Grid novel */
        .novel-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(340px, 1fr)); gap: 2rem; margin: 2rem 0; }
        .novel-card { background: white; border-radius: 32px; overflow: hidden; transition: 0.25s ease; box-shadow: 0 12px 20px -12px rgba(0, 0, 0, 0.2); display: flex; flex-direction: column; }
        .card-header { height: 120px; display: flex; align-items: center; justify-content: center; flex-direction: column; color: white; text-shadow: 1px 1px 3px rgba(0,0,0,0.3); border-radius: 32px 32px 0 0; }
        .card-header i { font-size: 2.6rem; margin-bottom: 6px; }
        .card-content { padding: 1.3rem; flex-grow: 1; }
        .card-title { font-family: 'Playfair Display', serif; font-size: 1.4rem; font-weight: 700; margin-bottom: 6px; }
        .tag-list { display: flex; flex-wrap: wrap; gap: 6px; margin: 10px 0; }
        .mini-tag { background: #e2f0ea; border-radius: 30px; font-size: 0.65rem; padding: 3px 10px; }
        .card-desc { font-size: 0.85rem; color: #336b4d; margin: 8px 0; display: -webkit-box; -webkit-line-clamp: 3; -webkit-box-orient: vertical; overflow: hidden; }
        .card-meta { font-size: 0.7rem; color: #588b6e; border-top: 1px solid #cde0d4; padding-top: 10px; margin-top: 8px; display: flex; justify-content: space-between; align-items: center; }
        .btn-read-large { background: #2e8b57; color: white; border: none; padding: 8px 20px; border-radius: 40px; font-weight: bold; cursor: pointer; transition: 0.2s; display: inline-flex; align-items: center; gap: 8px; font-size: 0.85rem; box-shadow: 0 2px 5px rgba(0,0,0,0.1); }
        .btn-read-large:hover { background: #1f6e46; transform: scale(1.02); }
        .empty-message { text-align: center; padding: 3rem; background: #e2f0e9; border-radius: 48px; color: #2f6a48; }

        /* HALAMAN BACA TERPISAH (READ PAGE) */
        .read-page {
            max-width: 900px;
            margin: 2rem auto;
            background: #fffef7;
            border-radius: 48px;
            padding: 2rem;
            box-shadow: 0 20px 35px rgba(0,0,0,0.1);
            border: 1px solid #bbdbc9;
        }
        .back-home-btn {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: #e2f0ea;
            padding: 8px 20px;
            border-radius: 40px;
            text-decoration: none;
            color: #1e5e39;
            font-weight: 500;
            margin-bottom: 2rem;
            transition: 0.2s;
        }
        .back-home-btn:hover { background: #cde0d4; }
        .story-title-page { font-family: 'Playfair Display', serif; font-size: 2.2rem; color: #135a33; margin-bottom: 0.5rem; }
        .story-meta-page { display: flex; gap: 20px; flex-wrap: wrap; margin: 1rem 0; border-bottom: 1px solid #cde0d4; padding-bottom: 1rem; }
        .story-content-page { white-space: pre-wrap; font-family: 'Inter', serif; line-height: 1.75; font-size: 1.05rem; margin-top: 2rem; background: #fafaf0; padding: 2rem; border-radius: 32px; }
        .story-content-page p { margin-bottom: 1rem; }
        .story-content-page .dialogue { background: #eef6f0; border-left: 4px solid #2e8b57; padding: 0.2rem 0.8rem; margin: 0.8rem 0; border-radius: 12px; }
        .story-content-page strong { font-weight: 700; color: #195f3a; }
        .story-content-page em { font-style: italic; color: #2e6d49; }
        footer { text-align: center; margin-top: 3rem; padding: 1.5rem; color: #327a54; }

        @media (max-width: 720px) { .container { padding: 1rem; } .navbar { flex-direction: column; } .read-page { margin: 1rem; padding: 1rem; } }
    </style>
</head>
<body>

<!-- Ini adalah tampilan utama (beranda + upload) -->
<div id="homepage">
    <div class="container">
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
                <h2>Perpus cerita bersama 🌍</h2>
                <p>Upload ceritamu → langsung bisa dibaca siapa pun (di perangkat ini). Setiap card punya tombol "Baca Sekarang" menuju halaman khusus.</p>
                <button class="btn-primary" id="scrollToUploadBtn"><i class="fas fa-feather-alt"></i> Tulis & Unggah</button>
            </div>
            <div style="font-size: 3rem;">📚✨</div>
        </div>

        <!-- Form Upload -->
        <div id="uploadSection">
            <h2 class="section-title"><i class="fas fa-pen-fancy"></i> Tambah Cerita Baru (Online)</h2>
            <div class="upload-card">
                <div class="form-grid">
                    <div class="form-group"><label>Judul Novel</label><input type="text" id="novelTitle" placeholder="Contoh: Rindu di Hutan Safir"></div>
                    <div class="form-group"><label>Nama Author</label><input type="text" id="novelAuthor" placeholder="Nama pena"></div>
                    <div class="form-group">
                        <label>Pilih Tag (bisa banyak) — 20+ tema</label>
                        <div class="tag-multiselect" id="tagMultiselectContainer"></div>
                    </div>
                    <div class="form-group"><label>Deskripsi Singkat (Card)</label><textarea rows="2" id="novelDesc" placeholder="Cuplikan cerita..."></textarea></div>
                    <div class="form-group"><label>Warna Card (Header)</label><div class="color-row"><input type="color" id="cardColor" value="#2b7a4b"><span>pilih warna</span></div></div>
                    <div class="form-group"><label>Upload File Novel (TXT/MD, maks 100MB)</label><input type="file" id="novelFile" accept=".txt,.md,.text/plain"><div class="file-info"><i class="fas fa-info-circle"></i> File teks UTF-8. Support *italic* , **bold** , "dialog". Maks 100MB.</div></div>
                </div>
                <div style="margin-top: 1.5rem; display: flex; justify-content: flex-end;"><button class="btn-primary" id="publishStoryBtn"><i class="fas fa-globe"></i> Terbitkan (Online)</button></div>
            </div>
        </div>

        <!-- Koleksi Cerita -->
        <div id="koleksiSection">
            <h2 class="section-title"><i class="fas fa-tree"></i> Koleksi Cerita (Semua Pengguna)</h2>
            <div id="novelGridContainer" class="novel-grid"><div class="empty-message"><i class="fas fa-leaf fa-2x"></i><p style="margin-top: 1rem;">Belum ada cerita. Jadilah penulis pertama ✍️</p></div></div>
        </div>
        <footer><i class="fas fa-seedling"></i> Leaf-Story — cerita yang kamu unggah langsung bisa dibaca orang lain (satu perangkat/browser). Setiap cerita punya halaman baca sendiri.</footer>
    </div>
</div>

<script>
    // ======================== DAFTAR TAG (20+ tema) ======================
    const ALL_TAGS = [
        "Fantasi", "Sci-fi", "Misteri", "Romantis", "Petualangan", "Horor", "Sejarah", "Legenda", 
        "Mythologie", "Slice of Life", "Storytelling", "Drama", "Komedi", "Thriller", "Psikologis",
        "Spiritual", "Young Adult", "Distopia", "Detektif", "Pernikahan", "Klasik", "Metropop", "Action"
    ];
    
    // Global state: array of stories (disimpan di localStorage -> shared antar user di browser yg sama)
    let stories = [];
    
    // Load dan simpan
    function loadStoriesFromStorage() {
        const stored = localStorage.getItem("leafStory_onlineCollection");
        if(stored) {
            stories = JSON.parse(stored);
        } else {
            stories = [];
        }
        renderAllCards();
    }
    
    function saveStoriesToStorage() {
        localStorage.setItem("leafStory_onlineCollection", JSON.stringify(stories));
    }
    
    // Render tag selector di form (multiselect)
    function renderTagSelector() {
        const container = document.getElementById("tagMultiselectContainer");
        if(!container) return;
        container.innerHTML = "";
        ALL_TAGS.forEach(tag => {
            const span = document.createElement("span");
            span.classList.add("tag-option-multi");
            span.innerText = tag;
            span.setAttribute("data-tagval", tag);
            span.addEventListener("click", (e) => {
                e.stopPropagation();
                span.classList.toggle("selected");
            });
            container.appendChild(span);
        });
    }
    
    function getSelectedTags() {
        const selectedSpans = document.querySelectorAll("#tagMultiselectContainer .tag-option-multi.selected");
        return Array.from(selectedSpans).map(s => s.getAttribute("data-tagval"));
    }
    
    // Fungsi parse markdown: *italic* , **bold** , "dialog"
    function parseMarkdownToHtml(text) {
        if(!text) return "";
        let safe = text.replace(/[&<>]/g, function(m) {
            if(m === '&') return '&amp;';
            if(m === '<') return '&lt;';
            if(m === '>') return '&gt;';
            return m;
        });
        safe = safe.replace(/\*\*(.+?)\*\*/gs, '<strong>$1</strong>');
        safe = safe.replace(/\*(.+?)\*/gs, '<em>$1</em>');
        safe = safe.replace(/"([^"]+)"/g, '<span class="dialogue">“$1”</span>');
        let paragraphs = safe.split(/\n\s*\n/);
        let parsed = paragraphs.map(p => {
            if(p.trim() === "") return "";
            let lineWithBreaks = p.replace(/\n/g, '<br>');
            return `<p>${lineWithBreaks}</p>`;
        }).join('');
        return parsed || `<p>${safe.replace(/\n/g, '<br>')}</p>`;
    }
    
    // Baca file teks
    function readTextFileContent(file) {
        return new Promise((resolve, reject) => {
            if(!file || (!file.name.endsWith(".txt") && !file.name.endsWith(".md") && file.type !== "text/plain")) {
                reject("Harap upload file .txt atau .md agar dapat dibaca.");
                return;
            }
            if(file.size > 100 * 1024 * 1024) reject("File terlalu besar (maks 100MB)");
            const reader = new FileReader();
            reader.onload = (e) => resolve(e.target.result);
            reader.onerror = () => reject("Gagal membaca file");
            reader.readAsText(file, "UTF-8");
        });
    }
    
    // Escape HTML untuk judul dll
    function escapeHtml(str) { if(!str) return ''; return str.replace(/[&<>]/g, function(m){ if(m==='&') return '&amp;'; if(m==='<') return '&lt;'; if(m==='>') return '&gt;'; return m;}); }
    
    // Render semua card di beranda (dengan tombol Baca Sekarang yang besar)
    function renderAllCards() {
        const container = document.getElementById("novelGridContainer");
        if(!stories.length) {
            container.innerHTML = `<div class="empty-message"><i class="fas fa-leaf fa-2x"></i><p style="margin-top:1rem;">Halaman kosong. Upload cerita pertamamu, nanti semua orang bisa membacanya!</p></div>`;
            return;
        }
        container.innerHTML = stories.map((story, idx) => {
            const headerStyle = `background: ${story.cardColor || "#2b7a4b"};`;
            const tagChips = (story.tags || []).slice(0, 3).map(t => `<span class="mini-tag">${escapeHtml(t)}</span>`).join('');
            const moreTag = (story.tags && story.tags.length > 3) ? `<span class="mini-tag">+${story.tags.length-3}</span>` : '';
            // tombol besar: "Baca Sekarang", akan redirect ke halaman baca dengan parameter id
            return `
                <div class="novel-card" data-id="${story.id}">
                    <div class="card-header" style="${headerStyle}"><i class="fas fa-book-open"></i><span style="font-size:0.7rem;">✨ cerita</span></div>
                    <div class="card-content">
                        <div class="card-title">${escapeHtml(story.title)}</div>
                        <div>oleh ${escapeHtml(story.author)}</div>
                        <div class="tag-list">${tagChips} ${moreTag}</div>
                        <div class="card-desc">${escapeHtml(story.description.substring(0, 110))}${story.description.length>110?'...':''}</div>
                        <div class="card-meta">
                            <span><i class="far fa-calendar-alt"></i> ${new Date(story.createdAt).toLocaleDateString()}</span>
                            <button class="btn-read-large" data-read-id="${story.id}"><i class="fas fa-book-reader"></i> Baca Sekarang</button>
                        </div>
                    </div>
                </div>
            `;
        }).join('');
        
        // Tambahkan event listener ke semua tombol "Baca Sekarang"
        document.querySelectorAll('.btn-read-large').forEach(btn => {
            btn.addEventListener('click', (e) => {
                e.stopPropagation();
                const storyId = btn.getAttribute('data-read-id');
                if(storyId) {
                    // redirect ke halaman baca dengan query param ?id=...
                    window.location.href = `?read=${storyId}`;
                }
            });
        });
    }
    
    // Fungsi untuk mengambil story by id
    function getStoryById(id) {
        return stories.find(s => s.id == id);
    }
    
    // ================ HALAMAN BACA TERPISAH (RENDER DINAMIS) =================
    function showReadPage(storyId) {
        const story = getStoryById(storyId);
        if(!story) {
            document.body.innerHTML = `<div style="text-align:center; margin-top: 4rem;"><h2>Cerita tidak ditemukan</h2><a href="/" style="color:#2e8b57;">← Kembali ke Beranda</a></div>`;
            return;
        }
        // Render halaman baca
        const parsedContent = parseMarkdownToHtml(story.fileContent || "Konten tidak tersedia.");
        document.body.innerHTML = `
            <div class="container" style="max-width: 1000px;">
                <a href="/" class="back-home-btn" id="backHomeBtn"><i class="fas fa-arrow-left"></i> Kembali ke Beranda</a>
                <div class="read-page">
                    <h1 class="story-title-page">${escapeHtml(story.title)}</h1>
                    <div class="story-meta-page">
                        <span><i class="fas fa-user-pen"></i> ${escapeHtml(story.author)}</span>
                        <span><i class="fas fa-calendar"></i> ${new Date(story.createdAt).toLocaleDateString()}</span>
                        <div class="tag-list" style="margin:0">${(story.tags || []).map(t => `<span class="mini-tag">${escapeHtml(t)}</span>`).join('')}</div>
                    </div>
                    <div class="story-content-page">
                        ${parsedContent || `<p>${escapeHtml(story.fileContent || "Tidak ada konten")}</p>`}
                    </div>
                </div>
                <footer><i class="fas fa-seedling"></i> Leaf-Story — baca cerita online</footer>
            </div>
        `;
        const backBtn = document.getElementById("backHomeBtn");
        if(backBtn) backBtn.addEventListener('click', (e) => {
            e.preventDefault();
            window.location.href = "/";
        });
    }
    
    // ================ ROUTING SEDERHANA =================
    function handleRouting() {
        const urlParams = new URLSearchParams(window.location.search);
        const readId = urlParams.get('read');
        if(readId) {
            // Pastikan data stories sudah di-load
            if(stories.length === 0) {
                // reload data dulu dari storage
                const stored = localStorage.getItem("leafStory_onlineCollection");
                if(stored) stories = JSON.parse(stored);
                else stories = [];
            }
            showReadPage(readId);
            return true;
        }
        return false;
    }
    
    // ================ EVENT PUBLISH (UPLOAD CERITA) =================
    async function publishStory() {
        const title = document.getElementById("novelTitle").value.trim();
        const author = document.getElementById("novelAuthor").value.trim();
        const description = document.getElementById("novelDesc").value.trim();
        const cardColor = document.getElementById("cardColor").value;
        const selectedTags = getSelectedTags();
        const fileInput = document.getElementById("novelFile");
        const file = fileInput.files[0];
        
        if(!title || !author) { alert("Judul dan Nama Author harus diisi!"); return; }
        if(selectedTags.length === 0) { alert("Pilih minimal satu tag!"); return; }
        if(!file) { alert("Upload file teks (.txt/.md) berisi novel."); return; }
        
        let fileContent = "";
        try {
            fileContent = await readTextFileContent(file);
        } catch(err) { alert(`Error: ${err}`); return; }
        
        const newStory = {
            id: Date.now(),
            title, author,
            tags: selectedTags,
            description: description || "Tidak ada deskripsi",
            cardColor: cardColor,
            createdAt: new Date().toISOString(),
            fileContent: fileContent.slice(0, 1000000) // aman 1 juta karakter
        };
        stories.unshift(newStory);
        saveStoriesToStorage();
        // reset form
        document.getElementById("novelTitle").value = "";
        document.getElementById("novelAuthor").value = "";
        document.getElementById("novelDesc").value = "";
        document.getElementById("cardColor").value = "#2b7a4b";
        document.querySelectorAll("#tagMultiselectContainer .tag-option-multi.selected").forEach(t => t.classList.remove("selected"));
        document.getElementById("novelFile").value = "";
        alert(`✨ "${title}" berhasil diterbitkan! Kini semua pengunjung (di perangkat ini) bisa membaca ceritamu.`);
        // refresh koleksi
        renderAllCards();
        // scroll
        document.getElementById("koleksiSection").scrollIntoView({ behavior: "smooth" });
    }
    
    // Inisialisasi halaman utama (jika bukan halaman baca)
    function initHomepage() {
        renderTagSelector();
        loadStoriesFromStorage();
        document.getElementById("publishStoryBtn")?.addEventListener("click", publishStory);
        document.getElementById("scrollToUploadBtn")?.addEventListener("click", () => {
            document.getElementById("uploadSection").scrollIntoView({ behavior: "smooth" });
        });
        document.getElementById("homeRefreshLink")?.addEventListener("click", (e) => {
            e.preventDefault();
            window.location.href = "/";
        });
    }
    
    // Memulai: cek routing dulu
    if(handleRouting()) {
        // sudah di halaman baca, tidak perlu init homepage lagi
    } else {
        // Tampilkan homepage
        initHomepage();
    }
</script>
</body>
</html>
