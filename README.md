<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Graysen</title>
<style>
:root{
    --bg:#f3ebdd;
    --card:#faf6ee;
    --text:#111111;
    --muted:#68645c;
    --green:#2f6b4f;
    --green-dark:#214d39;
    --border:#d8cfbf;
    --white:#ffffff;
    --shadow:0 15px 40px rgba(0,0,0,.08);
}
*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}
html{
    scroll-behavior:smooth;
}
body{
    font-family:Arial, Helvetica, sans-serif;
    background:var(--bg);
    color:var(--text);
    line-height:1.6;
}
button,
input,
textarea{
    font:inherit;
}
button{
    cursor:pointer;
}
a{
    color:inherit;
    text-decoration:none;
}
/* NAVIGATION */
header{
    position:sticky;
    top:0;
    z-index:1000;
    background:rgba(243,235,221,.94);
    backdrop-filter:blur(15px);
    border-bottom:1px solid var(--border);
}
.nav{
    max-width:1250px;
    margin:auto;
    padding:18px 25px;
    display:flex;
    align-items:center;
    justify-content:space-between;
}
.logo{
    font-size:25px;
    font-weight:800;
    letter-spacing:-1px;
}
.logo span{
    color:var(--green);
}
.nav-links{
    display:flex;
    gap:10px;
    list-style:none;
}
.nav-links button{
    border:0;
    background:transparent;
    padding:10px 15px;
    border-radius:10px;
    font-weight:600;
    color:var(--text);
}
.nav-links button:hover,
.nav-links button.active{
    background:var(--green);
    color:white;
}
.mobile-menu{
    display:none;
    border:0;
    background:transparent;
    font-size:25px;
}
/* PAGE SYSTEM */
.page{
    display:none;
}
.page.active{
    display:block;
}
/* HERO */
.hero{
    max-width:1250px;
    margin:auto;
    min-height:650px;
    padding:100px 25px;
    display:grid;
    grid-template-columns:1.3fr .7fr;
    gap:50px;
    align-items:center;
}
.hero-small{
    color:var(--green);
    font-weight:800;
    text-transform:uppercase;
    letter-spacing:3px;
    margin-bottom:15px;
}
.hero h1{
    font-size:clamp(70px,12vw,170px);
    line-height:.85;
    letter-spacing:-8px;
    margin-bottom:30px;
}
.hero p{
    max-width:650px;
    color:var(--muted);
    font-size:20px;
}
.hero-card{
    background:var(--green);
    color:white;
    min-height:420px;
    border-radius:35px;
    padding:35px;
    display:flex;
    flex-direction:column;
    justify-content:space-between;
    box-shadow:var(--shadow);
}
.profile-image{
    width:100%;
    height:270px;
    object-fit:cover;
    border-radius:22px;
    background:rgba(255,255,255,.12);
}
.hero-card h2{
    font-size:35px;
}
/* CONTENT */
.container{
    max-width:1250px;
    margin:auto;
    padding:80px 25px;
}
.section-title{
    font-size:60px;
    line-height:1;
    letter-spacing:-3px;
    margin-bottom:15px;
}
.section-description{
    color:var(--muted);
    max-width:700px;
    margin-bottom:45px;
}
.grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:25px;
}
.card{
    background:var(--card);
    border:1px solid var(--border);
    border-radius:25px;
    padding:30px;
    box-shadow:0 8px 25px rgba(0,0,0,.04);
}
.card h3{
    font-size:27px;
    margin-bottom:10px;
}
.card p{
    color:var(--muted);
}
/* BUTTONS */
.primary{
    border:0;
    background:var(--green);
    color:white;
    padding:14px 21px;
    border-radius:12px;
    font-weight:800;
}
.primary:hover{
    background:var(--green-dark);
}
.secondary{
    border:1px solid var(--border);
    background:var(--card);
    padding:13px 20px;
    border-radius:12px;
    font-weight:700;
}
.button-row{
    display:flex;
    gap:12px;
    flex-wrap:wrap;
}
/* PHOTOGRAPHY */
.photo-grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:18px;
}
.photo{
    position:relative;
    aspect-ratio:1/1;
    overflow:hidden;
    border-radius:20px;
    cursor:pointer;
    background:#ddd;
}
.photo img{
    width:100%;
    height:100%;
    object-fit:cover;
    transition:.35s;
}
.photo:hover img{
    transform:scale(1.05);
}
/* RESEARCH */
.research-list{
    display:grid;
    gap:20px;
}
.research-item{
    background:var(--card);
    border:1px solid var(--border);
    padding:25px;
    border-radius:20px;
}
.research-item h3{
    margin-bottom:8px;
}
.research-item p{
    color:var(--muted);
}
/* EDITOR */
.editor{
    display:none;
    position:fixed;
    inset:0;
    z-index:5000;
    background:rgba(0,0,0,.6);
    padding:20px;
    overflow:auto;
}
.editor.open{
    display:block;
}
.editor-box{
    background:var(--bg);
    max-width:900px;
    margin:30px auto;
    border-radius:30px;
    padding:30px;
}
.editor-header{
    display:flex;
    justify-content:space-between;
    align-items:center;
    gap:20px;
    margin-bottom:25px;
}
.editor-header h2{
    font-size:35px;
}
.close{
    border:0;
    background:transparent;
    font-size:30px;
}
.editor-section{
    background:var(--card);
    border:1px solid var(--border);
    padding:25px;
    border-radius:20px;
    margin-bottom:20px;
}
.editor-section h3{
    margin-bottom:15px;
}
label{
    display:block;
    font-weight:700;
    margin-bottom:7px;
}
input,
textarea{
    width:100%;
    padding:13px;
    border:1px solid var(--border);
    border-radius:10px;
    background:white;
    color:black;
    margin-bottom:15px;
}
textarea{
    min-height:130px;
    resize:vertical;
}
.editor-photo-grid{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:10px;
}
.editor-photo{
    position:relative;
    aspect-ratio:1;
}
.editor-photo img{
    width:100%;
    height:100%;
    object-fit:cover;
    border-radius:10px;
}
.delete-photo{
    position:absolute;
    right:5px;
    top:5px;
    width:30px;
    height:30px;
    border:0;
    border-radius:50%;
    background:#111;
    color:white;
    font-weight:bold;
}
.status{
    margin-top:15px;
    padding:15px;
    border-radius:12px;
    background:#e7dfd0;
    display:none;
}
.status.show{
    display:block;
}
/* LIGHTBOX */
.lightbox{
    display:none;
    position:fixed;
    inset:0;
    z-index:6000;
    background:rgba(0,0,0,.9);
    align-items:center;
    justify-content:center;
    padding:20px;
}
.lightbox.open{
    display:flex;
}
.lightbox img{
    max-width:95%;
    max-height:90vh;
    object-fit:contain;
    border-radius:10px;
}
.lightbox-close{
    position:absolute;
    top:20px;
    right:25px;
    border:0;
    background:transparent;
    color:white;
    font-size:40px;
}
/* FOOTER */
footer{
    border-top:1px solid var(--border);
    margin-top:80px;
    padding:35px 25px;
    color:var(--muted);
}
.footer-inner{
    max-width:1250px;
    margin:auto;
    display:flex;
    justify-content:space-between;
    gap:20px;
}
/* RESPONSIVE */
@media(max-width:850px){
    .nav-links{
        display:none;
        position:absolute;
        top:70px;
        left:15px;
        right:15px;
        background:var(--card);
        border:1px solid var(--border);
        border-radius:15px;
        padding:10px;
        flex-direction:column;
        box-shadow:var(--shadow);
    }
    .nav-links.open{
        display:flex;
    }
    .mobile-menu{
        display:block;
    }
    .hero{
        grid-template-columns:1fr;
        padding-top:65px;
    }
    .hero h1{
        letter-spacing:-5px;
    }
    .grid{
        grid-template-columns:1fr;
    }
    .photo-grid{
        grid-template-columns:repeat(2,1fr);
    }
    .editor-photo-grid{
        grid-template-columns:repeat(3,1fr);
    }
    .footer-inner{
        flex-direction:column;
    }
}
@media(max-width:500px){
    .container{
        padding:55px 18px;
    }
    .hero{
        padding:55px 18px;
    }
    .section-title{
        font-size:45px;
    }
    .photo-grid{
        gap:10px;
    }
    .editor-box{
        padding:20px;
        margin:10px auto;
    }
}
</style>
</head>
<body>
<header>
    <nav class="nav">
        <div class="logo">
            Graysen<span>.</span>
        </div>
        <button class="mobile-menu" id="mobileMenu">☰</button>
        <ul class="nav-links" id="navLinks">
            <li><button class="nav-button active" data-page="home">Home</button></li>
            <li><button class="nav-button" data-page="photography">Photography</button></li>
            <li><button class="nav-button" data-page="research">Political Research</button></li>
            <li><button class="nav-button" data-page="newspaper">Newspaper</button></li>
        </ul>
    </nav>
</header>
<main>
<!-- HOME -->
<section class="page active" id="home">
    <div class="hero">
        <div>
            <div class="hero-small">
                Personal Portfolio
            </div>
            <h1 id="heroName">
                Graysen
            </h1>
            <p id="bioText">
                Welcome to my portfolio. This website showcases my photography,
                political research, newspaper work, and other projects.
            </p>
            <br>
            <div class="button-row">
                <button class="primary" onclick="showPage('photography')">
                    View Photography
                </button>
                <button class="secondary" onclick="openEditor()">
                    Edit Portfolio
                </button>
            </div>
        </div>
        <div class="hero-card">
            <img
                id="profileImage"
                class="profile-image"
                alt="Profile photo"
            >
            <div>
                <h2>Creative work.</h2>
                <p>Research. Photography. Journalism.</p>
            </div>
        </div>
    </div>
</section>
<!-- PHOTOGRAPHY -->
<section class="page" id="photography">
    <div class="container">
        <div class="hero-small">
            Photography
        </div>
        <h2 class="section-title">
            Moments I've captured.
        </h2>
        <p class="section-description">
            A collection of photography and visual work.
        </p>
        <div class="photo-grid" id="photoGrid"></div>
    </div>
</section>
<!-- RESEARCH -->
<section class="page" id="research">
    <div class="container">
        <div class="hero-small">
            Political Research
        </div>
        <h2 class="section-title">
            Research & ideas.
        </h2>
        <p class="section-description">
            Research projects, writing, and topics I've explored.
        </p>
        <div class="research-list" id="researchList"></div>
    </div>
</section>
<!-- NEWSPAPER -->
<section class="page" id="newspaper">
    <div class="container">
        <div class="hero-small">
            Newspaper
        </div>
        <h2 class="section-title" id="newspaperTitle">
            Journalism.
        </h2>
        <p class="section-description" id="newspaperDescription">
            Writing and newspaper work.
        </p>
        <div class="card">
            <h3>
                Featured Article
            </h3>
            <br>
            <a
                id="newspaperLink"
                class="primary"
                href="#"
                target="_blank"
                rel="noopener"
            >
                Read Article
            </a>
        </div>
    </div>
</section>
</main>
<footer>
    <div class="footer-inner">
        <div>
            © <span id="year"></span> Graysen
        </div>
        <button class="secondary" onclick="openEditor()">
            Edit Portfolio
        </button>
    </div>
</footer>
<!-- EDITOR -->
<div class="editor" id="editor">
    <div class="editor-box">
        <div class="editor-header">
            <h2>Edit Portfolio</h2>
            <button class="close" onclick="closeEditor()">
                ×
            </button>
        </div>
        <!-- GITHUB SETTINGS -->
        <div class="editor-section">
            <h3>GitHub Settings</h3>
            <p style="color:#68645c;margin-bottom:15px;">
                These settings tell the editor which GitHub file should be updated.
                Your GitHub token is never saved into this website.
            </p>
            <label>
                GitHub Username
            </label>
            <input
                id="githubOwner"
                placeholder="your-github-username"
            >
            <label>
                Repository
            </label>
            <input
                id="githubRepo"
                placeholder="your-portfolio-repository"
            >
            <label>
                Branch
            </label>
            <input
                id="githubBranch"
                value="main"
            >
            <label>
                GitHub Personal Access Token
            </label>
            <input
                id="githubToken"
                type="password"
                placeholder="Paste your GitHub token when saving"
            >
        </div>
        <!-- BASIC INFO -->
        <div class="editor-section">
            <h3>Basic Information</h3>
            <label>
                Name
            </label>
            <input
                id="editName"
                value="Graysen"
            >
            <label>
                Bio
            </label>
            <textarea id="editBio"></textarea>
            <label>
                Profile Photo
            </label>
            <input
                id="profileUpload"
                type="file"
                accept="image/*"
            >
        </div>
        <!-- PHOTOS -->
        <div class="editor-section">
            <h3>Photography</h3>
            <p style="color:#68645c;margin-bottom:15px;">
                Maximum 25 photos. Photos are automatically compressed before
                being saved.
            </p>
            <input
                id="photoUpload"
                type="file"
                accept="image/*"
                multiple
            >
            <div
                class="editor-photo-grid"
                id="editorPhotoGrid"
            ></div>
        </div>
        <!-- RESEARCH -->
        <div class="editor-section">
            <h3>Political Research</h3>
            <div id="researchEditor"></div>
            <button
                class="secondary"
                onclick="addResearch()"
            >
                + Add Research
            </button>
        </div>
        <!-- NEWSPAPER -->
        <div class="editor-section">
            <h3>Newspaper</h3>
            <label>
                Article Title
            </label>
            <input id="editNewspaperTitle">
            <label>
                Description
            </label>
            <textarea id="editNewspaperDescription"></textarea>
            <label>
                Article Link
            </label>
            <input
                id="editNewspaperLink"
                placeholder="https://..."
            >
        </div>
        <div class="button-row">
            <button
                class="primary"
                onclick="saveToGitHub()"
            >
                Save Changes To GitHub
            </button>
            <button
                class="secondary"
                onclick="closeEditor()"
            >
                Cancel
            </button>
        </div>
        <div class="status" id="saveStatus"></div>
    </div>
</div>
<!-- LIGHTBOX -->
<div class="lightbox" id="lightbox">
    <button
        class="lightbox-close"
        onclick="closeLightbox()"
    >
        ×
    </button>
    <img id="lightboxImage" alt="Expanded photograph">
</div>
<script>
/*
=========================================================
PORTFOLIO DATA
=========================================================
This section is what the editor updates.
When you save, the entire HTML file on GitHub is rewritten
with the updated DATA object.
=========================================================
*/
const DATA = {
    name: "Graysen",
    bio:
        "Welcome to my portfolio. This website showcases my photography, political research, newspaper work, and other projects.",
    profileImage: "",
    photos: [],
    research: [
        {
            title: "Political Research",
            description:
                "Research projects and political topics I have explored."
        }
    ],
    newspaper: {
        title: "Journalism.",
        description: "Writing and newspaper work.",
        link: "#"
    }
};
/*
=========================================================
GITHUB CONFIG
=========================================================
*/
const GITHUB_CONFIG = {
    owner: "",
    repo: "",
    branch: "main"
};
/*
=========================================================
STARTUP
=========================================================
*/
document.getElementById("year").textContent =
    new Date().getFullYear();
renderSite();
/*
=========================================================
PAGE NAVIGATION
=========================================================
*/
document.querySelectorAll(".nav-button").forEach(button => {
    button.addEventListener("click", () => {
        showPage(button.dataset.page);
    });
});
function showPage(page){
    document.querySelectorAll(".page").forEach(p => {
        p.classList.remove("active");
    });
    document.getElementById(page).classList.add("active");
    document.querySelectorAll(".nav-button").forEach(button => {
        button.classList.toggle(
            "active",
            button.dataset.page === page
        );
    });
    document.getElementById("navLinks").classList.remove("open");
    window.scrollTo({
        top:0,
        behavior:"smooth"
    });
}
/*
=========================================================
MOBILE MENU
=========================================================
*/
document.getElementById("mobileMenu").onclick = () => {
    document
        .getElementById("navLinks")
        .classList.toggle("open");
};
/*
=========================================================
RENDER WEBSITE
=========================================================
*/
function renderSite(){
    document.getElementById("heroName").textContent =
        DATA.name || "Graysen";
    document.getElementById("bioText").textContent =
        DATA.bio || "";
    document.getElementById("newspaperTitle").textContent =
        DATA.newspaper.title || "Journalism.";
    document.getElementById("newspaperDescription").textContent =
        DATA.newspaper.description || "";
    const newspaperLink =
        document.getElementById("newspaperLink");
    newspaperLink.href =
        DATA.newspaper.link || "#";
    renderProfile();
    renderPhotos();
    renderResearch();
}
/*
=========================================================
PROFILE
=========================================================
*/
function renderProfile(){
    const image =
        document.getElementById("profileImage");
    if(DATA.profileImage){
        image.src = DATA.profileImage;
    }else{
        image.removeAttribute("src");
        image.style.display = "none";
    }
}
/*
=========================================================
PHOTOGRAPHY
=========================================================
*/
function renderPhotos(){
    const grid =
        document.getElementById("photoGrid");
    grid.innerHTML = "";
    if(DATA.photos.length === 0){
        grid.innerHTML = `
            <div class="card">
                <h3>No photographs yet.</h3>
                <p>
                    Open the editor to add photography.
                </p>
            </div>
        `;
        return;
    }
    DATA.photos.forEach((photo,index) => {
        const item =
            document.createElement("div");
        item.className = "photo";
        item.innerHTML = `
            <img
                src="${photo}"
                alt="Photography ${index + 1}"
            >
        `;
        item.onclick = () => {
            document.getElementById(
                "lightboxImage"
            ).src = photo;
            document
                .getElementById("lightbox")
                .classList.add("open");
        };
        grid.appendChild(item);
    });
}
/*
=========================================================
RESEARCH
=========================================================
*/
function renderResearch(){
    const list =
        document.getElementById("researchList");
    list.innerHTML = "";
    DATA.research.forEach(item => {
        const article =
            document.createElement("div");
        article.className = "research-item";
        article.innerHTML = `
            <h3>${escapeHTML(item.title)}</h3>
            <p>${escapeHTML(item.description)}</p>
        `;
        list.appendChild(article);
    });
}
/*
=========================================================
LIGHTBOX
=========================================================
*/
function closeLightbox(){
    document
        .getElementById("lightbox")
        .classList.remove("open");
}
/*
=========================================================
EDITOR
=========================================================
*/
function openEditor(){
    const code =
        prompt("Enter edit code:");
    if(code !== "4547"){
        if(code !== null){
            alert("Incorrect edit code.");
        }
        return;
    }
    loadEditor();
    document
        .getElementById("editor")
        .classList.add("open");
}
function closeEditor(){
    document
        .getElementById("editor")
        .classList.remove("open");
}
/*
=========================================================
LOAD EDITOR
=========================================================
*/
function loadEditor(){
    document.getElementById("editName").value =
        DATA.name;
    document.getElementById("editBio").value =
        DATA.bio;
    document.getElementById("editNewspaperTitle").value =
        DATA.newspaper.title;
    document.getElementById("editNewspaperDescription").value =
        DATA.newspaper.description;
    document.getElementById("editNewspaperLink").value =
        DATA.newspaper.link;
    renderEditorPhotos();
    renderResearchEditor();
}
/*
=========================================================
PROFILE IMAGE UPLOAD
=========================================================
*/
document
    .getElementById("profileUpload")
    .addEventListener("change", async function(){
        const file = this.files[0];
        if(!file) return;
        DATA.profileImage =
            await compressImage(file, 700, .78);
        alert("Profile photo added.");
    });
/*
=========================================================
PHOTO UPLOAD
=========================================================
*/
document
    .getElementById("photoUpload")
    .addEventListener("change", async function(){
        const files =
            Array.from(this.files);
        if(DATA.photos.length + files.length > 25){
            alert("You can have a maximum of 25 photos.");
            return;
        }
        for(const file of files){
            const compressed =
                await compressImage(
                    file,
                    1200,
                    .72
                );
            DATA.photos.push(compressed);
        }
        renderEditorPhotos();
        this.value = "";
    });
/*
=========================================================
IMAGE COMPRESSION
=========================================================
*/
function compressImage(
    file,
    maxSize,
    quality
){
    return new Promise((resolve,reject) => {
        const reader =
            new FileReader();
        reader.onload = event => {
            const image =
                new Image();
            image.onload = () => {
                let width =
                    image.width;
                let height =
                    image.height;
                if(width > maxSize || height > maxSize){
                    const ratio =
                        Math.min(
                            maxSize / width,
                            maxSize / height
                        );
                    width *= ratio;
                    height *= ratio;
                }
                const canvas =
                    document.createElement("canvas");
                canvas.width =
                    Math.round(width);
                canvas.height =
                    Math.round(height);
                const ctx =
                    canvas.getContext("2d");
                ctx.drawImage(
                    image,
                    0,
                    0,
                    canvas.width,
                    canvas.height
                );
                resolve(
                    canvas.toDataURL(
                        "image/jpeg",
                        quality
                    )
                );
            };
            image.onerror = reject;
            image.src =
                event.target.result;
        };
        reader.onerror = reject;
        reader.readAsDataURL(file);
    });
}
/*
=========================================================
EDITOR PHOTOS
=========================================================
*/
function renderEditorPhotos(){
    const grid =
        document.getElementById(
            "editorPhotoGrid"
        );
    grid.innerHTML = "";
    DATA.photos.forEach((photo,index) => {
        const item =
            document.createElement("div");
        item.className =
            "editor-photo";
        item.innerHTML = `
            <img src="${photo}">
            <button
                class="delete-photo"
                onclick="deletePhoto(${index})"
            >
                ×
            </button>
        `;
        grid.appendChild(item);
    });
}
function deletePhoto(index){
    if(!confirm("Delete this photo?")) return;
    DATA.photos.splice(index,1);
    renderEditorPhotos();
}
/*
=========================================================
RESEARCH EDITOR
=========================================================
*/
function renderResearchEditor(){
    const editor =
        document.getElementById(
            "researchEditor"
        );
    editor.innerHTML = "";
    DATA.research.forEach((item,index) => {
        const wrapper =
            document.createElement("div");
        wrapper.style.marginBottom = "20px";
        wrapper.innerHTML = `
            <label>
                Research Title
            </label>
            <input
                value="${escapeAttribute(item.title)}"
                oninput="DATA.research[${index}].title=this.value"
            >
            <label>
                Description
            </label>
            <textarea
                oninput="DATA.research[${index}].description=this.value"
            >${escapeHTML(item.description)}</textarea>
            <button
                class="secondary"
                onclick="deleteResearch(${index})"
            >
                Delete Research
            </button>
        `;
        editor.appendChild(wrapper);
    });
}
function addResearch(){
    DATA.research.push({
        title:"New Research",
        description:"Add your research description here."
    });
    renderResearchEditor();
}
function deleteResearch(index){
    DATA.research.splice(index,1);
    renderResearchEditor();
}
/*
=========================================================
SAVE EDITOR VALUES
=========================================================
*/
function collectEditorData(){
    DATA.name =
        document.getElementById(
            "editName"
        ).value.trim();
    DATA.bio =
        document.getElementById(
            "editBio"
        ).value.trim();
    DATA.newspaper.title =
        document.getElementById(
            "editNewspaperTitle"
        ).value.trim();
    DATA.newspaper.description =
        document.getElementById(
            "editNewspaperDescription"
        ).value.trim();
    DATA.newspaper.link =
        document.getElementById(
            "editNewspaperLink"
        ).value.trim();
}
/*
=========================================================
GITHUB SAVE
=========================================================
*/
async function saveToGitHub(){
    collectEditorData();
    const owner =
        document.getElementById(
            "githubOwner"
        ).value.trim();
    const repo =
        document.getElementById(
            "githubRepo"
        ).value.trim();
    const branch =
        document.getElementById(
            "githubBranch"
        ).value.trim() || "main";
    const token =
        document.getElementById(
            "githubToken"
        ).value.trim();
    const status =
        document.getElementById(
            "saveStatus"
        );
    if(!owner || !repo || !token){
        alert(
            "Enter your GitHub username, repository, and token."
        );
        return;
    }
    status.classList.add("show");
    status.textContent =
        "Preparing your website...";
    try{
        /*
        Get the current index.html from GitHub.
        */
        const apiURL =
            `https://api.github.com/repos/${owner}/${repo}/contents/index.html?ref=${encodeURIComponent(branch)}`;
        const getResponse =
            await fetch(apiURL,{
                headers:{
                    "Authorization":
                        `Bearer ${token}`,
                    "Accept":
                        "application/vnd.github+json"
                }
            });
        if(!getResponse.ok){
            throw new Error(
                "Could not access index.html. Check your GitHub information and token."
            );
        }
        const file =
            await getResponse.json();
        /*
        Decode current HTML.
        */
        const currentHTML =
            decodeBase64(file.content);
        /*
        Replace the DATA section.
        */
        const newHTML =
            replacePortfolioData(
                currentHTML,
                DATA
            );
        /*
        Encode the updated HTML.
        */
        const encodedHTML =
            encodeBase64(newHTML);
        status.textContent =
            "Uploading updated website to GitHub...";
        /*
        Send updated index.html back to GitHub.
        */
        const putResponse =
            await fetch(
                `https://api.github.com/repos/${owner}/${repo}/contents/index.html`,
                {
                    method:"PUT",
                    headers:{
                        "Authorization":
                            `Bearer ${token}`,
                        "Accept":
                            "application/vnd.github+json",
                        "Content-Type":
                            "application/json"
                    },
                    body:JSON.stringify({
                        message:
                            "Update portfolio",
                        content:
                            encodedHTML,
                        sha:
                            file.sha,
                        branch:
                            branch
                    })
                }
            );
        if(!putResponse.ok){
            const error =
                await putResponse.json();
            throw new Error(
                error.message ||
                "GitHub rejected the update."
            );
        }
        status.textContent =
            "✓ Saved! Your website has been updated on GitHub. Everyone will see the changes after GitHub Pages publishes them.";
        renderSite();
    }catch(error){
        console.error(error);
        status.textContent =
            "Error: " + error.message;
    }
}
/*
=========================================================
REPLACE DATA INSIDE HTML
=========================================================
*/
function replacePortfolioData(
    html,
    data
){
    const startMarker =
        "const DATA = {";
    const endMarker =
        "};";
    const start =
        html.indexOf(startMarker);
    if(start === -1){
        throw new Error(
            "Could not find the DATA section in index.html."
        );
    }
    const end =
        html.indexOf(
            endMarker,
            start
        );
    if(end === -1){
        throw new Error(
            "Could not find the end of the DATA section."
        );
    }
    const dataCode =
        "const DATA = " +
        JSON.stringify(data,null,4) +
        ";";
    return (
        html.substring(0,start) +
        dataCode +
        html.substring(end + endMarker.length)
    );
}
/*
=========================================================
BASE64 HELPERS
=========================================================
*/
function encodeBase64(text){
    return btoa(
        unescape(
            encodeURIComponent(text)
        )
    );
}
function decodeBase64(base64){
    return decodeURIComponent(
        escape(
            atob(
                base64.replace(/\n/g,"")
            )
        )
    );
}
/*
=========================================================
HTML SAFETY
=========================================================
*/
function escapeHTML(text){
    return String(text)
        .replace(/&/g,"&amp;")
        .replace(/</g,"&lt;")
        .replace(/>/g,"&gt;")
        .replace(/"/g,"&quot;")
        .replace(/'/g,"&#039;");
}
function escapeAttribute(text){
    return escapeHTML(text);
}
/*
=========================================================
ESCAPE LIGHTBOX WITH ESC KEY
=========================================================
*/
document.addEventListener(
    "keydown",
    event => {
        if(event.key === "Escape"){
            closeLightbox();
            closeEditor();
        }
    }
);
</script>
</body>
</html>