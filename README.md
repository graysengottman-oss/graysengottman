<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>My Portfolio</title>
<style>
/* =========================
   COLOR SYSTEM
========================= */
:root {
    --tan: #F3EBDD;
    --tan-light: #FAF7F0;
    --black: #111111;
    --green: #2F6B4F;
    --green-dark: #24533D;
    --green-light: #DCE8DF;
    --border: #D8CDBB;
    --white: #FFFFFF;
}
/* =========================
   RESET
========================= */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
html {
    scroll-behavior: smooth;
}
body {
    font-family: Arial, Helvetica, sans-serif;
    background: var(--tan);
    color: var(--black);
    line-height: 1.6;
}
/* =========================
   HEADER
========================= */
header {
    position: sticky;
    top: 0;
    z-index: 1000;
    background: rgba(243, 235, 221, 0.96);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
}
.nav {
    max-width: 1200px;
    margin: auto;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 18px 22px;
}
.logo {
    font-size: 24px;
    font-weight: 800;
    letter-spacing: -1px;
}
.logo span {
    color: var(--green);
}
.nav-links {
    display: flex;
    gap: 8px;
    list-style: none;
}
.nav-links button {
    border: none;
    background: transparent;
    padding: 9px 13px;
    font-size: 14px;
    font-weight: 700;
    color: var(--black);
    border-radius: 8px;
    cursor: pointer;
    transition: 0.2s;
}
.nav-links button:hover,
.nav-links button.active {
    background: var(--green);
    color: white;
}
/* =========================
   MAIN
========================= */
main {
    max-width: 1200px;
    margin: auto;
    padding: 50px 22px 80px;
}
.page {
    display: none;
}
.page.active {
    display: block;
}
/* =========================
   HOME
========================= */
.hero {
    min-height: 70vh;
    display: grid;
    grid-template-columns: 1.2fr 0.8fr;
    gap: 60px;
    align-items: center;
}
.hero h1 {
    font-size: clamp(48px, 8vw, 88px);
    line-height: 0.95;
    letter-spacing: -4px;
    margin-bottom: 24px;
}
.hero h1 span {
    color: var(--green);
}
.hero p {
    max-width: 650px;
    font-size: 19px;
    color: #3e3e3e;
}
.hero-image {
    width: 100%;
    max-width: 390px;
    aspect-ratio: 1 / 1;
    object-fit: cover;
    border-radius: 24px;
    border: 8px solid var(--tan-light);
    box-shadow:
        0 15px 40px rgba(0,0,0,0.12);
}
/* =========================
   SECTION HEADERS
========================= */
.section-header {
    margin-bottom: 35px;
}
.section-header h2 {
    font-size: clamp(38px, 6vw, 60px);
    letter-spacing: -2px;
}
.section-header p {
    color: #555;
    margin-top: 8px;
}
/* =========================
   BUTTONS
========================= */
.button {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    border: none;
    background: var(--green);
    color: white;
    padding: 12px 18px;
    border-radius: 9px;
    font-weight: 700;
    cursor: pointer;
    transition: 0.2s;
}
.button:hover {
    background: var(--green-dark);
    transform: translateY(-1px);
}
.button.secondary {
    background: var(--green-light);
    color: var(--green-dark);
}
.button.danger {
    background: #8b3030;
}
/* =========================
   PHOTO GRID
========================= */
.photo-grid {
    display: grid;
    grid-template-columns:
        repeat(auto-fill, minmax(220px, 1fr));
    gap: 18px;
}
.photo-card {
    position: relative;
    aspect-ratio: 1 / 1;
    overflow: hidden;
    border-radius: 14px;
    background: var(--tan-light);
    border: 1px solid var(--border);
    cursor: pointer;
    transition: 0.25s;
}
.photo-card:hover {
    transform: translateY(-4px);
    box-shadow:
        0 12px 30px rgba(0,0,0,0.12);
}
.photo-card img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
}
/* =========================
   RESEARCH
========================= */
.document-grid {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(280px, 1fr));
    gap: 20px;
}
.document-card {
    background: var(--tan-light);
    border: 1px solid var(--border);
    border-radius: 15px;
    padding: 24px;
    transition: 0.2s;
}
.document-card:hover {
    border-color: var(--green);
    transform: translateY(-3px);
}
.document-card h3 {
    margin-bottom: 8px;
}
.document-card p {
    color: #555;
    margin-bottom: 18px;
}
/* =========================
   NEWSPAPER
========================= */
.article-list {
    display: grid;
    gap: 18px;
}
.article {
    background: var(--tan-light);
    border: 1px solid var(--border);
    border-left: 5px solid var(--green);
    padding: 24px;
    border-radius: 12px;
}
.article h3 {
    margin-bottom: 8px;
}
.article p {
    color: #555;
    margin-bottom: 15px;
}
.article a {
    color: var(--green-dark);
    font-weight: 700;
    text-decoration: none;
}
.article a:hover {
    text-decoration: underline;
}
/* =========================
   EDIT BUTTON
========================= */
.edit-button {
    position: fixed;
    right: 20px;
    bottom: 20px;
    z-index: 2000;
    background: var(--green);
    color: white;
    border: none;
    padding: 15px 20px;
    border-radius: 50px;
    font-size: 15px;
    font-weight: 800;
    cursor: pointer;
    box-shadow:
        0 8px 25px rgba(0,0,0,0.2);
    transition: 0.2s;
}
.edit-button:hover {
    background: var(--green-dark);
    transform: translateY(-2px);
}
/* =========================
   MODAL
========================= */
.modal {
    position: fixed;
    inset: 0;
    z-index: 3000;
    display: none;
    align-items: center;
    justify-content: center;
    padding: 20px;
    background: rgba(17,17,17,0.55);
    backdrop-filter: blur(5px);
}
.modal.show {
    display: flex;
}
.modal-box {
    width: 100%;
    max-width: 700px;
    max-height: 90vh;
    overflow-y: auto;
    background: var(--tan-light);
    border-radius: 18px;
    padding: 28px;
    box-shadow:
        0 25px 80px rgba(0,0,0,0.25);
}
.modal-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 25px;
}
.close {
    border: none;
    background: transparent;
    font-size: 28px;
    cursor: pointer;
    color: var(--black);
}
/* =========================
   EDIT TABS
========================= */
.tabs {
    display: flex;
    gap: 7px;
    margin-bottom: 25px;
    overflow-x: auto;
}
.tab {
    white-space: nowrap;
    border: none;
    background: var(--green-light);
    color: var(--green-dark);
    padding: 10px 14px;
    border-radius: 8px;
    font-weight: 700;
    cursor: pointer;
}
.tab.active {
    background: var(--green);
    color: white;
}
.editor {
    display: none;
}
.editor.active {
    display: block;
}
/* =========================
   FORMS
========================= */
label {
    display: block;
    margin-bottom: 6px;
    font-size: 14px;
    font-weight: 700;
}
input,
textarea {
    width: 100%;
    padding: 12px 13px;
    margin-bottom: 16px;
    border-radius: 8px;
    border: 1px solid var(--border);
    background: white;
    color: var(--black);
    font-family: inherit;
    font-size: 15px;
    outline: none;
}
input:focus,
textarea:focus {
    border-color: var(--green);
    box-shadow:
        0 0 0 3px rgba(47,107,79,0.12);
}
textarea {
    min-height: 130px;
    resize: vertical;
}
/* =========================
   PHOTO UPLOAD
========================= */
.upload-area {
    border: 2px dashed var(--green);
    background: var(--green-light);
    padding: 35px 20px;
    text-align: center;
    border-radius: 12px;
    margin-bottom: 20px;
}
.upload-area p {
    margin-bottom: 15px;
    color: var(--green-dark);
}
input[type="file"] {
    border: none;
    background: transparent;
    padding: 0;
}
/* =========================
   STATUS
========================= */
.status {
    margin-top: 15px;
    padding: 12px;
    background: var(--green-light);
    color: var(--green-dark);
    border-radius: 8px;
    font-size: 14px;
    display: none;
}
.status.show {
    display: block;
}
/* =========================
   FOOTER
========================= */
footer {
    border-top: 1px solid var(--border);
    padding: 35px 22px;
    text-align: center;
    color: #555;
}
footer span {
    color: var(--green);
    font-weight: 700;
}
/* =========================
   MOBILE
========================= */
@media (max-width: 750px) {
    .nav {
        flex-direction: column;
        gap: 14px;
    }
    .nav-links {
        width: 100%;
        justify-content: center;
        flex-wrap: wrap;
    }
    .hero {
        grid-template-columns: 1fr;
        text-align: center;
        min-height: auto;
        padding: 35px 0;
    }
    .hero p {
        margin: auto;
    }
    .hero-image {
        margin: auto;
        max-width: 300px;
    }
    .hero h1 {
        letter-spacing: -2px;
    }
    main {
        padding-top: 30px;
    }
    .edit-button {
        right: 15px;
        bottom: 15px;
    }
}
</style>
</head>
<body>
<!-- =========================
     HEADER
========================= -->
<header>
    <nav class="nav">
        <div class="logo">
            My<span>Portfolio</span>
        </div>
        <ul class="nav-links">
            <li>
                <button class="nav-btn active"
                        data-page="home">
                    Home
                </button>
            </li>
            <li>
                <button class="nav-btn"
                        data-page="photography">
                    Photography
                </button>
            </li>
            <li>
                <button class="nav-btn"
                        data-page="research">
                    Political Research
                </button>
            </li>
            <li>
                <button class="nav-btn"
                        data-page="newspaper">
                    Newspaper
                </button>
            </li>
        </ul>
    </nav>
</header>
<!-- =========================
     MAIN
========================= -->
<main>
<!-- HOME -->
<section id="home" class="page active">
    <div class="hero">
        <div>
            <h1>
                My<br>
                <span>Portfolio.</span>
            </h1>
            <p id="bioText">
                Welcome to my portfolio. This is where I share
                my photography, research, writing, and projects.
            </p>
        </div>
        <div>
            <img
                id="profileImage"
                class="hero-image"
                src=""
                alt="Profile photo"
            >
        </div>
    </div>
</section>
<!-- PHOTOGRAPHY -->
<section id="photography" class="page">
    <div class="section-header">
        <h2>Photography</h2>
        <p>
            A collection of my photography.
        </p>
    </div>
    <div
        id="photoGrid"
        class="photo-grid">
    </div>
</section>
<!-- RESEARCH -->
<section id="research" class="page">
    <div class="section-header">
        <h2>Political Research</h2>
        <p>
            Research, documents, and projects.
        </p>
    </div>
    <div
        id="documentGrid"
        class="document-grid">
    </div>
</section>
<!-- NEWSPAPER -->
<section id="newspaper" class="page">
    <div class="section-header">
        <h2>Newspaper</h2>
        <p>
            Articles and writing.
        </p>
    </div>
    <div
        id="articleList"
        class="article-list">
    </div>
</section>
</main>
<!-- =========================
     FOOTER
========================= -->
<footer>
    <p>
        © <span id="year"></span> My Portfolio
    </p>
</footer>
<!-- =========================
     EDIT BUTTON
========================= -->
<button
    class="edit-button"
    id="editButton">
    EDIT
</button>
<!-- =========================
     EDIT MODAL
========================= -->
<div
    class="modal"
    id="editModal">
    <div class="modal-box">
        <div class="modal-header">
            <h2>Edit Website</h2>
            <button
                class="close"
                id="closeModal">
                ×
            </button>
        </div>
        <!-- TABS -->
        <div class="tabs">
            <button
                class="tab active"
                data-editor="homeEditor">
                Home
            </button>
            <button
                class="tab"
                data-editor="photoEditor">
                Photos
            </button>
            <button
                class="tab"
                data-editor="researchEditor">
                Research
            </button>
            <button
                class="tab"
                data-editor="newspaperEditor">
                Newspaper
            </button>
        </div>
        <!-- HOME EDITOR -->
        <div
            id="homeEditor"
            class="editor active">
            <label>
                About Me
            </label>
            <textarea
                id="bioInput"
                placeholder="Write your bio...">
            </textarea>
            <label>
                Profile Photo
            </label>
            <input
                type="file"
                id="profileInput"
                accept="image/*">
            <button
                class="button"
                id="saveHome">
                Save Home
            </button>
        </div>
        <!-- PHOTO EDITOR -->
        <div
            id="photoEditor"
            class="editor">
            <div class="upload-area">
                <p>
                    Add up to 25 photos.
                    Photos are automatically compressed
                    before being stored.
                </p>
                <input
                    type="file"
                    id="photoInput"
                    accept="image/*"
                    multiple>
            </div>
            <button
                class="button"
                id="clearPhotos">
                Clear All Photos
            </button>
        </div>
        <!-- RESEARCH EDITOR -->
        <div
            id="researchEditor"
            class="editor">
            <label>
                Research Title
            </label>
            <input
                id="researchTitle"
                placeholder="Research project title">
            <label>
                Description
            </label>
            <textarea
                id="researchDescription"
                placeholder="Describe your research...">
            </textarea>
            <label>
                Document
            </label>
            <input
                type="file"
                id="researchFile">
            <button
                class="button"
                id="saveResearch">
                Add Research
            </button>
        </div>
        <!-- NEWSPAPER EDITOR -->
        <div
            id="newspaperEditor"
            class="editor">
            <label>
                Article Title
            </label>
            <input
                id="articleTitle"
                placeholder="Article title">
            <label>
                Description
            </label>
            <textarea
                id="articleDescription"
                placeholder="Short description">
            </textarea>
            <label>
                Article URL
            </label>
            <input
                id="articleURL"
                placeholder="https://example.com">
            <button
                class="button"
                id="saveArticle">
                Add Article
            </button>
        </div>
        <div
            class="status"
            id="status">
        </div>
    </div>
</div>
<script>
/* =========================
   SETTINGS
========================= */
const EDIT_CODE = "4547";
const MAX_PHOTOS = 25;
/* =========================
   DATABASE
========================= */
let db;
const request = indexedDB.open(
    "PortfolioDatabase",
    1
);
request.onupgradeneeded = function(event) {
    db = event.target.result;
    if (!db.objectStoreNames.contains("photos")) {
        db.createObjectStore(
            "photos",
            {
                keyPath: "id",
                autoIncrement: true
            }
        );
    }
    if (!db.objectStoreNames.contains("research")) {
        db.createObjectStore(
            "research",
            {
                keyPath: "id",
                autoIncrement: true
            }
        );
    }
    if (!db.objectStoreNames.contains("articles")) {
        db.createObjectStore(
            "articles",
            {
                keyPath: "id",
                autoIncrement: true
            }
        );
    }
    if (!db.objectStoreNames.contains("settings")) {
        db.createObjectStore(
            "settings",
            {
                keyPath: "key"
            }
        );
    }
};
request.onsuccess = function(event) {
    db = event.target.result;
    loadEverything();
};
/* =========================
   PAGE NAVIGATION
========================= */
const navButtons =
    document.querySelectorAll(".nav-btn");
const pages =
    document.querySelectorAll(".page");
navButtons.forEach(button => {
    button.addEventListener("click", () => {
        const target =
            button.dataset.page;
        navButtons.forEach(btn =>
            btn.classList.remove("active")
        );
        button.classList.add("active");
        pages.forEach(page => {
            page.classList.remove("active");
            if (page.id === target) {
                page.classList.add("active");
            }
        });
        window.scrollTo({
            top: 0,
            behavior: "smooth"
        });
    });
});
/* =========================
   EDIT MODAL
========================= */
const editButton =
    document.getElementById("editButton");
const editModal =
    document.getElementById("editModal");
const closeModal =
    document.getElementById("closeModal");
editButton.addEventListener("click", () => {
    const code =
        prompt("Enter your edit code:");
    if (code === EDIT_CODE) {
        editModal.classList.add("show");
    } else if (code !== null) {
        alert("Incorrect code.");
    }
});
closeModal.addEventListener("click", () => {
    editModal.classList.remove("show");
});
editModal.addEventListener("click", event => {
    if (event.target === editModal) {
        editModal.classList.remove("show");
    }
});
/* =========================
   EDIT TABS
========================= */
const tabs =
    document.querySelectorAll(".tab");
const editors =
    document.querySelectorAll(".editor");
tabs.forEach(tab => {
    tab.addEventListener("click", () => {
        const target =
            tab.dataset.editor;
        tabs.forEach(t =>
            t.classList.remove("active")
        );
        tab.classList.add("active");
        editors.forEach(editor => {
            editor.classList.remove("active");
            if (editor.id === target) {
                editor.classList.add("active");
            }
        });
    });
});
/* =========================
   IMAGE COMPRESSION
========================= */
function compressImage(
    file,
    maxSize = 1200,
    quality = 0.55
) {
    return new Promise((resolve, reject) => {
        const reader =
            new FileReader();
        reader.onload = event => {
            const img =
                new Image();
            img.onload = () => {
                let width =
                    img.width;
                let height =
                    img.height;
                if (width > maxSize ||
                    height > maxSize) {
                    const scale =
                        Math.min(
                            maxSize / width,
                            maxSize / height
                        );
                    width *= scale;
                    height *= scale;
                }
                const canvas =
                    document.createElement("canvas");
                canvas.width =
                    width;
                canvas.height =
                    height;
                const ctx =
                    canvas.getContext("2d");
                ctx.drawImage(
                    img,
                    0,
                    0,
                    width,
                    height
                );
                canvas.toBlob(
                    blob => {
                        if (blob) {
                            resolve(blob);
                        } else {
                            reject(
                                new Error(
                                    "Compression failed."
                                )
                            );
                        }
                    },
                    "image/jpeg",
                    quality
                );
            };
            img.onerror = reject;
            img.src =
                event.target.result;
        };
        reader.onerror = reject;
        reader.readAsDataURL(file);
    });
}
/* =========================
   DATABASE HELPER
========================= */
function transaction(
    storeName,
    mode = "readonly"
) {
    return db.transaction(
        storeName,
        mode
    ).objectStore(storeName);
}
/* =========================
   SETTINGS
========================= */
function saveSetting(key, value) {
    return new Promise(resolve => {
        const store =
            transaction(
                "settings",
                "readwrite"
            );
        store.put({
            key,
            value
        });
        resolve();
    });
}
function getSetting(key) {
    return new Promise(resolve => {
        const store =
            transaction("settings");
        const request =
            store.get(key);
        request.onsuccess =
            () => {
                resolve(
                    request.result
                        ? request.result.value
                        : null
                );
            };
    });
}
/* =========================
   HOME
========================= */
document
    .getElementById("saveHome")
    .addEventListener("click", async () => {
        const bio =
            document
                .getElementById("bioInput")
                .value
                .trim();
        await saveSetting(
            "bio",
            bio
        );
        const file =
            document
                .getElementById("profileInput")
                .files[0];
        if (file) {
            const compressed =
                await compressImage(
                    file,
                    1200,
                    0.55
                );
            const reader =
                new FileReader();
            reader.onload =
                async () => {
                    await saveSetting(
                        "profileImage",
                        reader.result
                    );
                    loadHome();
                };
            reader.readAsDataURL(
                compressed
            );
        } else {
            loadHome();
        }
        showStatus(
            "Home page saved!"
        );
    });
async function loadHome() {
    const bio =
        await getSetting("bio");
    const profile =
        await getSetting("profileImage");
    if (bio !== null) {
        document
            .getElementById("bioText")
            .textContent = bio;
        document
            .getElementById("bioInput")
            .value = bio;
    }
    if (profile) {
        document
            .getElementById("profileImage")
            .src = profile;
    }
}
/* =========================
   PHOTOS
========================= */
document
    .getElementById("photoInput")
    .addEventListener("change", async event => {
        const files =
            [...event.target.files];
        if (!files.length) return;
        const current =
            await getAll("photos");
        if (
            current.length +
            files.length >
            MAX_PHOTOS
        ) {
            alert(
                `You can have up to ${MAX_PHOTOS} photos.`
            );
            return;
        }
        for (const file of files) {
            try {
                const compressed =
                    await compressImage(
                        file,
                        1200,
                        0.55
                    );
                await addItem(
                    "photos",
                    {
                        image: compressed
                    }
                );
            } catch(error) {
                console.error(error);
            }
        }
        event.target.value = "";
        loadPhotos();
        showStatus(
            "Photos added and compressed!"
        );
    });
function addItem(
    storeName,
    item
) {
    return new Promise(resolve => {
        const store =
            transaction(
                storeName,
                "readwrite"
            );
        const request =
            store.add(item);
        request.onsuccess =
            () => resolve();
    });
}
function getAll(storeName) {
    return new Promise(resolve => {
        const store =
            transaction(storeName);
        const request =
            store.getAll();
        request.onsuccess =
            () => resolve(
                request.result
            );
    });
}
async function loadPhotos() {
    const grid =
        document.getElementById(
            "photoGrid"
        );
    grid.innerHTML = "";
    const photos =
        await getAll("photos");
    photos.forEach(photo => {
        const card =
            document.createElement("div");
        card.className =
            "photo-card";
        const img =
            document.createElement("img");
        img.src =
            URL.createObjectURL(
                photo.image
            );
        img.alt =
            "Portfolio photograph";
        card.appendChild(img);
        grid.appendChild(card);
    });
}
document
    .getElementById("clearPhotos")
    .addEventListener("click", async () => {
        const confirmed =
            confirm(
                "Delete all photos?"
            );
        if (!confirmed) return;
        const store =
            transaction(
                "photos",
                "readwrite"
            );
        store.clear();
        loadPhotos();
        showStatus(
            "All photos cleared."
        );
    });
/* =========================
   RESEARCH
========================= */
document
    .getElementById("saveResearch")
    .addEventListener("click", async () => {
        const title =
            document
                .getElementById(
                    "researchTitle"
                )
                .value
                .trim();
        const description =
            document
                .getElementById(
                    "researchDescription"
                )
                .value
                .trim();
        const file =
            document
                .getElementById(
                    "researchFile"
                )
                .files[0];
        if (!title) {
            alert(
                "Please enter a title."
            );
            return;
        }
        await addItem(
            "research",
            {
                title,
                description,
                file: file || null
            }
        );
        document
            .getElementById(
                "researchTitle"
            ).value = "";
        document
            .getElementById(
                "researchDescription"
            ).value = "";
        document
            .getElementById(
                "researchFile"
            ).value = "";
        loadResearch();
        showStatus(
            "Research added!"
        );
    });
async function loadResearch() {
    const grid =
        document.getElementById(
            "documentGrid"
        );
    grid.innerHTML = "";
    const documents =
        await getAll("research");
    documents.forEach(doc => {
        const card =
            document.createElement("div");
        card.className =
            "document-card";
        const title =
            document.createElement("h3");
        title.textContent =
            doc.title;
        const description =
            document.createElement("p");
        description.textContent =
            doc.description || "";
        card.appendChild(title);
        card.appendChild(description);
        if (doc.file) {
            const link =
                document.createElement("a");
            link.className =
                "button";
            link.textContent =
                "Open Document";
            link.href =
                URL.createObjectURL(
                    doc.file
                );
            link.target =
                "_blank";
            card.appendChild(link);
        }
        grid.appendChild(card);
    });
}
/* =========================
   NEWSPAPER
========================= */
document
    .getElementById("saveArticle")
    .addEventListener("click", async () => {
        const title =
            document
                .getElementById(
                    "articleTitle"
                )
                .value
                .trim();
        const description =
            document
                .getElementById(
                    "articleDescription"
                )
                .value
                .trim();
        const url =
            document
                .getElementById(
                    "articleURL"
                )
                .value
                .trim();
        if (!title) {
            alert(
                "Please enter an article title."
            );
            return;
        }
        await addItem(
            "articles",
            {
                title,
                description,
                url
            }
        );
        document
            .getElementById(
                "articleTitle"
            ).value = "";
        document
            .getElementById(
                "articleDescription"
            ).value = "";
        document
            .getElementById(
                "articleURL"
            ).value = "";
        loadArticles();
        showStatus(
            "Article added!"
        );
    });
async function loadArticles() {
    const list =
        document.getElementById(
            "articleList"
        );
    list.innerHTML = "";
    const articles =
        await getAll("articles");
    articles.forEach(article => {
        const item =
            document.createElement("article");
        item.className =
            "article";
        const title =
            document.createElement("h3");
        title.textContent =
            article.title;
        const description =
            document.createElement("p");
        description.textContent =
            article.description || "";
        item.appendChild(title);
        item.appendChild(description);
        if (article.url) {
            const link =
                document.createElement("a");
            link.href =
                article.url;
            link.target =
                "_blank";
            link.rel =
                "noopener noreferrer";
            link.textContent =
                "Read Article →";
            item.appendChild(link);
        }
        list.appendChild(item);
    });
}
/* =========================
   STATUS MESSAGE
========================= */
function showStatus(message) {
    const status =
        document.getElementById(
            "status"
        );
    status.textContent =
        message;
    status.classList.add("show");
    setTimeout(() => {
        status.classList.remove(
            "show"
        );
    }, 3000);
}
/* =========================
   LOAD EVERYTHING
========================= */
async function loadEverything() {
    await loadHome();
    await loadPhotos();
    await loadResearch();
    await loadArticles();
    document
        .getElementById("year")
        .textContent =
        new Date().getFullYear();
}
/* =========================
   KEYBOARD SHORTCUT
========================= */
document.addEventListener(
    "keydown",
    event => {
        if (
            event.key === "Escape" &&
            editModal.classList.contains("show")
        ) {
            editModal.classList.remove(
                "show"
            );
        }
    }
);
</script>
</body>
</html>