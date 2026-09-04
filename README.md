<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<title>Portfolio</title>
<style>
:root{
    --bg:#09090b;
    --surface:#111113;
    --surface2:#18181b;
    --border:#27272a;
    --text:#fafafa;
    --muted:#a1a1aa;
    --soft:#71717a;
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
    background:var(--bg);
    color:var(--text);
    font-family:
        -apple-system,
        BlinkMacSystemFont,
        "Segoe UI",
        Roboto,
        Helvetica,
        Arial,
        sans-serif;
    line-height:1.5;
    -webkit-font-smoothing:antialiased;
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
}
img{
    max-width:100%;
}
/* ========================================
   HEADER
======================================== */
header{
    position:sticky;
    top:0;
    z-index:100;
    background:rgba(9,9,11,.88);
    backdrop-filter:blur(20px);
    -webkit-backdrop-filter:blur(20px);
    border-bottom:1px solid rgba(255,255,255,.08);
}
.nav{
    width:100%;
    max-width:1150px;
    margin:auto;
    padding:
        max(12px, env(safe-area-inset-top))
        16px
        12px;
}
.nav-top{
    display:flex;
    justify-content:space-between;
    align-items:center;
    gap:15px;
}
.logo{
    font-size:19px;
    font-weight:750;
    letter-spacing:-.5px;
    text-decoration:none;
    white-space:nowrap;
}
.menu{
    display:flex;
    gap:5px;
    overflow-x:auto;
    padding-top:10px;
    scrollbar-width:none;
}
.menu::-webkit-scrollbar{
    display:none;
}
.menu a{
    flex:0 0 auto;
    text-decoration:none;
    color:#a1a1aa;
    font-size:13px;
    padding:8px 11px;
    border-radius:9px;
}
.menu a:hover,
.menu a:active{
    color:white;
    background:#1c1c1f;
}
/* ========================================
   CONTAINER
======================================== */
.container{
    width:100%;
    max-width:1150px;
    margin:auto;
    padding:0 17px;
}
section{
    padding:70px 0;
}
.eyebrow{
    color:#71717a;
    font-size:11px;
    font-weight:750;
    text-transform:uppercase;
    letter-spacing:2px;
    margin-bottom:12px;
}
.section-title{
    font-size:34px;
    line-height:1.05;
    letter-spacing:-1.5px;
    margin-bottom:10px;
}
.section-description{
    color:var(--muted);
    font-size:15px;
    max-width:650px;
}
/* ========================================
   HERO
======================================== */
.hero{
    min-height:calc(100svh - 105px);
    display:flex;
    align-items:center;
    padding:55px 0 70px;
}
.hero-grid{
    display:flex;
    flex-direction:column;
    gap:38px;
}
.profile-wrap{
    display:flex;
    justify-content:center;
    order:-1;
}
.profile-photo,
.profile-placeholder{
    width:min(270px,78vw);
    aspect-ratio:1;
    border-radius:26px;
}
.profile-photo{
    object-fit:cover;
    border:1px solid #303035;
    box-shadow:0 25px 70px rgba(0,0,0,.45);
}
.profile-placeholder{
    display:flex;
    align-items:center;
    justify-content:center;
    text-align:center;
    padding:25px;
    color:#71717a;
    border:1px solid var(--border);
    background:linear-gradient(
        145deg,
        #18181b,
        #0f0f11
    );
}
.hero h1{
    font-size:clamp(52px,15vw,90px);
    line-height:.91;
    letter-spacing:-5px;
    margin-bottom:22px;
    word-break:break-word;
}
.hero-bio{
    color:#b9b9bf;
    font-size:16px;
    line-height:1.7;
    max-width:650px;
}
.hero-buttons{
    display:flex;
    flex-direction:column;
    gap:10px;
    margin-top:25px;
}
.primary-button,
.secondary-button{
    display:flex;
    justify-content:center;
    align-items:center;
    min-height:48px;
    padding:12px 18px;
    border-radius:12px;
    text-decoration:none;
    font-size:14px;
    font-weight:700;
}
.primary-button{
    background:white;
    color:#080808;
}
.secondary-button{
    background:#18181b;
    border:1px solid var(--border);
}
/* ========================================
   PHOTOGRAPHY
======================================== */
.photo-grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:7px;
    margin-top:30px;
}
.photo-card{
    width:100%;
    aspect-ratio:1/1;
    overflow:hidden;
    background:#141416;
    border-radius:10px;
}
.photo-card img{
    width:100%;
    height:100%;
    object-fit:cover;
    transition:transform .4s ease;
}
.photo-card:active img,
.photo-card:hover img{
    transform:scale(1.035);
}
/* ========================================
   RESEARCH
======================================== */
.research-list{
    display:flex;
    flex-direction:column;
    gap:11px;
    margin-top:30px;
}
.research-item{
    display:flex;
    flex-direction:column;
    gap:15px;
    padding:18px;
    border:1px solid var(--border);
    background:var(--surface);
    border-radius:15px;
}
.research-info h3{
    font-size:17px;
    margin-bottom:5px;
}
.research-info p{
    color:var(--muted);
    font-size:13px;
}
.research-link{
    display:flex;
    justify-content:center;
    align-items:center;
    width:100%;
    min-height:43px;
    border:1px solid #35353a;
    border-radius:10px;
    text-decoration:none;
    font-size:13px;
    font-weight:650;
    background:#18181b;
}
/* ========================================
   NEWSPAPER
======================================== */
.news-grid{
    display:grid;
    grid-template-columns:1fr;
    gap:12px;
    margin-top:30px;
}
.news-card{
    padding:21px;
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:17px;
}
.news-date{
    color:#71717a;
    font-size:10px;
    font-weight:750;
    letter-spacing:1.3px;
    text-transform:uppercase;
    margin-bottom:9px;
}
.news-card h3{
    font-size:20px;
    line-height:1.25;
}
.news-card a{
    display:inline-block;
    margin-top:15px;
    color:white;
    text-decoration:none;
    font-size:13px;
    font-weight:650;
}
/* ========================================
   EMPTY
======================================== */
.empty{
    padding:40px 20px;
    border:1px dashed #303035;
    border-radius:15px;
    text-align:center;
    color:#71717a;
    font-size:14px;
}
/* ========================================
   FOOTER
======================================== */
footer{
    border-top:1px solid var(--border);
    padding:
        25px
        0
        calc(30px + env(safe-area-inset-bottom));
    color:#71717a;
    font-size:12px;
}
.footer-inner{
    display:flex;
    flex-direction:column;
    gap:5px;
}
/* ========================================
   BIG EDIT BUTTON
======================================== */
.edit-button{
    position:fixed;
    z-index:150;
    right:18px;
    bottom:
        calc(18px + env(safe-area-inset-bottom));
    min-width:75px;
    height:48px;
    padding:0 18px;
    border:1px solid #4a4a50;
    border-radius:14px;
    background:#ffffff;
    color:#080808;
    font-size:13px;
    font-weight:800;
    letter-spacing:.4px;
    box-shadow:
        0 10px 35px rgba(0,0,0,.5);
    transition:
        transform .2s ease,
        box-shadow .2s ease;
}
.edit-button:active{
    transform:scale(.96);
}
.edit-button:hover{
    transform:translateY(-2px);
}
/* ========================================
   MODALS
======================================== */
.modal{
    position:fixed;
    inset:0;
    z-index:500;
    display:none;
    align-items:flex-end;
    justify-content:center;
    background:rgba(0,0,0,.7);
    backdrop-filter:blur(12px);
    -webkit-backdrop-filter:blur(12px);
}
.modal.active{
    display:flex;
}
.modal-box{
    width:100%;
    max-height:92svh;
    overflow:auto;
    background:#111113;
    border:
        1px solid
        #303035;
    border-radius:
        22px
        22px
        0
        0;
    padding:
        24px
        18px
        calc(24px + env(safe-area-inset-bottom));
    box-shadow:
        0 -20px 70px rgba(0,0,0,.5);
}
.modal-header{
    display:flex;
    align-items:center;
    justify-content:space-between;
    margin-bottom:22px;
}
.modal-header h2{
    font-size:22px;
    letter-spacing:-.5px;
}
.close{
    width:38px;
    height:38px;
    border:1px solid #303035;
    border-radius:10px;
    background:#1a1a1d;
    color:white;
    font-size:22px;
}
/* ========================================
   TABS
======================================== */
.tabs{
    display:flex;
    gap:6px;
    overflow-x:auto;
    margin-bottom:23px;
    scrollbar-width:none;
}
.tabs::-webkit-scrollbar{
    display:none;
}
.tab{
    flex:0 0 auto;
    padding:9px 12px;
    border:1px solid #303035;
    border-radius:9px;
    background:#18181b;
    color:#a1a1aa;
    font-size:12px;
}
.tab.active{
    color:#050505;
    background:white;
    border-color:white;
}
/* ========================================
   FORMS
======================================== */
.form-group{
    margin-bottom:17px;
}
.form-group label{
    display:block;
    color:#d4d4d8;
    font-size:12px;
    font-weight:700;
    margin-bottom:7px;
}
input,
textarea{
    width:100%;
    border:1px solid #303035;
    border-radius:11px;
    background:#18181b;
    color:white;
    padding:13px;
    outline:none;
    font-size:15px;
}
textarea{
    min-height:125px;
    resize:vertical;
}
input:focus,
textarea:focus{
    border-color:#65656b;
}
input[type="file"]{
    font-size:13px;
    padding:10px;
}
.status{
    margin-top:7px;
    color:#71717a;
    font-size:11px;
    line-height:1.5;
}
.warning{
    padding:13px;
    margin-bottom:18px;
    border:1px solid #3d3526;
    border-radius:11px;
    background:#1b1813;
    color:#b9aa8e;
    font-size:12px;
}
.form-actions{
    display:flex;
    gap:8px;
    margin-top:22px;
}
.save-button,
.cancel-button{
    flex:1;
    min-height:46px;
    border-radius:11px;
    font-weight:750;
    font-size:13px;
}
.save-button{
    background:white;
    color:black;
    border:0;
}
.cancel-button{
    background:#18181b;
    color:white;
    border:1px solid #303035;
}
/* ========================================
   DESKTOP
======================================== */
@media(min-width:700px){
    .nav{
        padding:16px 25px;
    }
    .nav-top{
        display:block;
    }
    .menu{
        position:absolute;
        right:25px;
        top:14px;
        padding:0;
    }
    .logo{
        font-size:21px;
    }
    .container{
        padding:0 25px;
    }
    section{
        padding:105px 0;
    }
    .hero{
        min-height:calc(100vh - 70px);
        padding:70px 0;
    }
    .hero-grid{
        display:grid;
        grid-template-columns:1.2fr .8fr;
        align-items:center;
        gap:80px;
    }
    .profile-wrap{
        order:0;
    }
    .profile-photo,
    .profile-placeholder{
        width:min(380px,100%);
        border-radius:30px;
    }
    .hero-buttons{
        flex-direction:row;
    }
    .primary-button,
    .secondary-button{
        min-height:45px;
        width:auto;
    }
    .photo-grid{
        grid-template-columns:repeat(3,1fr);
        gap:14px;
    }
    .photo-card{
        border-radius:15px;
    }
    .research-item{
        flex-direction:row;
        align-items:center;
        justify-content:space-between;
    }
    .research-link{
        width:auto;
        padding:0 17px;
    }
    .news-grid{
        grid-template-columns:1fr 1fr;
    }
    .footer-inner{
        flex-direction:row;
        justify-content:space-between;
    }
    .modal{
        align-items:center;
        padding:20px;
    }
    .modal-box{
        width:min(700px,100%);
        max-height:90vh;
        border-radius:22px;
        padding:28px;
    }
}
</style>
</head>
<body>
<header>
    <nav class="nav">
        <div class="nav-top">
            <a href="#home" class="logo" id="navLogo">
                Portfolio
            </a>
        </div>
        <div class="menu">
            <a href="#home">Home</a>
            <a href="#photography">Photography</a>
            <a href="#research">Research</a>
            <a href="#newspaper">Newspaper</a>
        </div>
    </nav>
</header>
<main>
<!-- ================= HOME ================= -->
<section id="home" class="hero">
    <div class="container">
        <div class="hero-grid">
            <div class="hero-content">
                <div class="eyebrow">
                    Portfolio
                </div>
                <h1 id="heroName">
                    Your Name
                </h1>
                <p
                    id="heroBio"
                    class="hero-bio"
                >
                    Welcome to my portfolio.
                    This is where I share my photography,
                    research, writing, and projects.
                </p>
                <div class="hero-buttons">
                    <a
                        href="#photography"
                        class="primary-button"
                    >
                        View Photography
                    </a>
                    <a
                        href="#newspaper"
                        class="secondary-button"
                    >
                        Newspaper
                    </a>
                </div>
            </div>
            <div class="profile-wrap">
                <div id="profileContainer"></div>
            </div>
        </div>
    </div>
</section>
<!-- ================= PHOTOGRAPHY ================= -->
<section id="photography">
    <div class="container">
        <div class="eyebrow">
            Visual Work
        </div>
        <h2 class="section-title">
            Photography
        </h2>
        <p class="section-description">
            A collection of my photography and visual work.
        </p>
        <div
            id="photoGallery"
            class="photo-grid"
        ></div>
    </div>
</section>
<!-- ================= RESEARCH ================= -->
<section id="research">
    <div class="container">
        <div class="eyebrow">
            Research
        </div>
        <h2 class="section-title">
            Political Research
        </h2>
        <p class="section-description">
            Research papers, documents, and projects.
        </p>
        <div
            id="researchList"
            class="research-list"
        ></div>
    </div>
</section>
<!-- ================= NEWSPAPER ================= -->
<section id="newspaper">
    <div class="container">
        <div class="eyebrow">
            Writing
        </div>
        <h2 class="section-title">
            Newspaper
        </h2>
        <p class="section-description">
            Articles and writing from my newspaper work.
        </p>
        <div
            id="newsList"
            class="news-grid"
        ></div>
    </div>
</section>
</main>
<footer>
    <div class="container footer-inner">
        <div>
            © <span id="footerName">Portfolio</span>
        </div>
        <div>
            Photography · Research · Writing
        </div>
    </div>
</footer>
<!-- ================= EDIT BUTTON ================= -->
<button
    class="edit-button"
    onclick="openCodeModal()"
>
    EDIT
</button>
<!-- ================= CODE MODAL ================= -->
<div
    class="modal"
    id="codeModal"
>
    <div class="modal-box">
        <div class="modal-header">
            <h2>
                Edit Portfolio
            </h2>
            <button
                class="close"
                onclick="closeModal('codeModal')"
            >
                ×
            </button>
        </div>
        <div class="form-group">
            <label>
                Enter Edit Code
            </label>
            <input
                id="editCode"
                type="password"
                inputmode="numeric"
                autocomplete="off"
                placeholder="Enter code"
            >
            <div
                id="codeError"
                class="status"
            ></div>
        </div>
        <div class="form-actions">
            <button
                class="cancel-button"
                onclick="closeModal('codeModal')"
            >
                Cancel
            </button>
            <button
                class="save-button"
                onclick="checkCode()"
            >
                Continue
            </button>
        </div>
    </div>
</div>
<!-- ================= EDITOR ================= -->
<div
    class="modal"
    id="editorModal"
>
    <div class="modal-box">
        <div class="modal-header">
            <h2>
                Edit Portfolio
            </h2>
            <button
                class="close"
                onclick="closeModal('editorModal')"
            >
                ×
            </button>
        </div>
        <div class="tabs">
            <button
                class="tab active"
                onclick="showTab('homeTab',this)"
            >
                Home
            </button>
            <button
                class="tab"
                onclick="showTab('photoTab',this)"
            >
                Photos
            </button>
            <button
                class="tab"
                onclick="showTab('researchTab',this)"
            >
                Research
            </button>
            <button
                class="tab"
                onclick="showTab('newsTab',this)"
            >
                Newspaper
            </button>
        </div>
        <!-- HOME -->
        <div
            id="homeTab"
            class="editor-tab"
        >
            <div class="form-group">
                <label>
                    Name
                </label>
                <input
                    id="editName"
                    type="text"
                >
            </div>
            <div class="form-group">
                <label>
                    Bio
                </label>
                <textarea
                    id="editBio"
                ></textarea>
            </div>
            <div class="form-group">
                <label>
                    Profile Photo
                </label>
                <input
                    id="profileInput"
                    type="file"
                    accept="image/*"
                >
                <div class="status">
                    Photos are automatically compressed
                    before being stored.
                </div>
            </div>
            <div class="form-actions">
                <button
                    class="save-button"
                    onclick="saveHome()"
                >
                    Save Changes
                </button>
            </div>
        </div>
        <!-- PHOTOS -->
        <div
            id="photoTab"
            class="editor-tab"
            style="display:none;"
        >
            <div class="warning">
                <strong>25-photo maximum.</strong>
                Your photos are automatically compressed
                to keep storage use low.
            </div>
            <div class="form-group">
                <label>
                    Add Photos
                </label>
                <input
                    id="photoInput"
                    type="file"
                    accept="image/*"
                    multiple
                >
                <div
                    id="photoStatus"
                    class="status"
                >
                    0 / 25 photos
                </div>
            </div>
            <div class="form-actions">
                <button
                    class="save-button"
                    onclick="addPhotos()"
                >
                    Add Photos
                </button>
            </div>
        </div>
        <!-- RESEARCH -->
        <div
            id="researchTab"
            class="editor-tab"
            style="display:none;"
        >
            <div class="form-group">
                <label>
                    Document Title
                </label>
                <input
                    id="researchTitle"
                    type="text"
                    placeholder="Research title"
                >
            </div>
            <div class="form-group">
                <label>
                    Description
                </label>
                <textarea
                    id="researchDescription"
                    placeholder="Short description"
                ></textarea>
            </div>
            <div class="form-group">
                <label>
                    Document
                </label>
                <input
                    id="researchFile"
                    type="file"
                    accept=".pdf,.doc,.docx,.txt"
                >
            </div>
            <div class="form-actions">
                <button
                    class="save-button"
                    onclick="addResearch()"
                >
                    Add Document
                </button>
            </div>
        </div>
        <!-- NEWSPAPER -->
        <div
            id="newsTab"
            class="editor-tab"
            style="display:none;"
        >
            <div class="form-group">
                <label>
                    Article Title
                </label>
                <input
                    id="articleTitle"
                    type="text"
                    placeholder="Article title"
                >
            </div>
            <div class="form-group">
                <label>
                    Date
                </label>
                <input
                    id="articleDate"
                    type="text"
                    placeholder="September 16, 2026"
                >
            </div>
            <div class="form-group">
                <label>
                    Article Link
                </label>
                <input
                    id="articleURL"
                    type="text"
                    placeholder="https://example.com"
                >
            </div>
            <div class="form-actions">
                <button
                    class="save-button"
                    onclick="addArticle()"
                >
                    Publish Article
                </button>
            </div>
        </div>
    </div>
</div>
<script>
/* =========================================================
   DATABASE
========================================================= */
const DB_NAME = "portfolioDatabase";
const DB_VERSION = 1;
const EDIT_CODE = "4547";
const MAX_PHOTOS = 25;
let db;
let data = {
    name:"Your Name",
    bio:
        "Welcome to my portfolio. " +
        "This is where I share my photography, " +
        "research, writing, and projects.",
    profilePhoto:null,
    photos:[],
    documents:[],
    articles:[],
    newspaperHasPublishedArticle:false
};
let objectURLs = [];
/* =========================================================
   OPEN DATABASE
========================================================= */
function openDatabase(){
    return new Promise((resolve,reject)=>{
        const request =
            indexedDB.open(
                DB_NAME,
                DB_VERSION
            );
        request.onupgradeneeded = event => {
            const database =
                event.target.result;
            if(!database.objectStoreNames.contains("settings")){
                database.createObjectStore(
                    "settings",
                    {keyPath:"key"}
                );
            }
            if(!database.objectStoreNames.contains("photos")){
                database.createObjectStore(
                    "photos",
                    {
                        keyPath:"id",
                        autoIncrement:true
                    }
                );
            }
            if(!database.objectStoreNames.contains("documents")){
                database.createObjectStore(
                    "documents",
                    {
                        keyPath:"id",
                        autoIncrement:true
                    }
                );
            }
            if(!database.objectStoreNames.contains("articles")){
                database.createObjectStore(
                    "articles",
                    {
                        keyPath:"id",
                        autoIncrement:true
                    }
                );
            }
        };
        request.onsuccess = event => {
            db = event.target.result;
            resolve(db);
        };
        request.onerror = () => {
            reject(request.error);
        };
    });
}
/* =========================================================
   DATABASE HELPERS
========================================================= */
function getAll(storeName){
    return new Promise((resolve,reject)=>{
        const transaction =
            db.transaction(
                storeName,
                "readonly"
            );
        const store =
            transaction.objectStore(
                storeName
            );
        const request =
            store.getAll();
        request.onsuccess = () => {
            resolve(request.result);
        };
        request.onerror = () => {
            reject(request.error);
        };
    });
}
function put(storeName,value){
    return new Promise((resolve,reject)=>{
        const transaction =
            db.transaction(
                storeName,
                "readwrite"
            );
        const request =
            transaction
                .objectStore(storeName)
                .put(value);
        request.onsuccess = () => {
            resolve(request.result);
        };
        request.onerror = () => {
            reject(request.error);
        };
    });
}
function add(storeName,value){
    return new Promise((resolve,reject)=>{
        const transaction =
            db.transaction(
                storeName,
                "readwrite"
            );
        const request =
            transaction
                .objectStore(storeName)
                .add(value);
        request.onsuccess = () => {
            resolve(request.result);
        };
        request.onerror = () => {
            reject(request.error);
        };
    });
}
/* =========================================================
   LOAD
========================================================= */
async function loadData(){
    await openDatabase();
    const settings =
        await getAll("settings");
    const photos =
        await getAll("photos");
    const documents =
        await getAll("documents");
    const articles =
        await getAll("articles");
    settings.forEach(setting=>{
        if(setting.key === "name")
            data.name = setting.value;
        if(setting.key === "bio")
            data.bio = setting.value;
        if(setting.key === "profilePhoto")
            data.profilePhoto = setting.value;
        if(setting.key === "newspaperHasPublishedArticle")
            data.newspaperHasPublishedArticle =
                setting.value;
    });
    data.photos = photos;
    data.documents = documents;
    data.articles = articles;
    renderEverything();
}
/* =========================================================
   OBJECT URL CLEANUP
========================================================= */
function clearObjectURLs(){
    objectURLs.forEach(url=>{
        URL.revokeObjectURL(url);
    });
    objectURLs = [];
}
/* =========================================================
   RENDER
========================================================= */
function renderEverything(){
    clearObjectURLs();
    document.getElementById("heroName").textContent =
        data.name;
    document.getElementById("heroBio").textContent =
        data.bio;
    document.getElementById("navLogo").textContent =
        data.name || "Portfolio";
    document.getElementById("footerName").textContent =
        data.name || "Portfolio";
    renderProfile();
    renderPhotos();
    renderResearch();
    renderNews();
    updatePhotoStatus();
}
/* =========================================================
   PROFILE
========================================================= */
function renderProfile(){
    const container =
        document.getElementById(
            "profileContainer"
        );
    container.innerHTML = "";
    if(data.profilePhoto){
        const img =
            document.createElement("img");
        const url =
            URL.createObjectURL(
                data.profilePhoto
            );
        objectURLs.push(url);
        img.src = url;
        img.className =
            "profile-photo";
        img.alt =
            "Profile photo";
        container.appendChild(img);
    }else{
        const placeholder =
            document.createElement("div");
        placeholder.className =
            "profile-placeholder";
        placeholder.textContent =
            "Add your profile photo using EDIT.";
        container.appendChild(
            placeholder
        );
    }
}
/* =========================================================
   PHOTOGRAPHY
========================================================= */
function renderPhotos(){
    const gallery =
        document.getElementById(
            "photoGallery"
        );
    gallery.innerHTML = "";
    if(data.photos.length === 0){
        gallery.innerHTML = `
            <div
                class="empty"
                style="grid-column:1/-1;"
            >
                No photography added yet.
            </div>
        `;
        return;
    }
    data.photos.forEach(photo=>{
        const card =
            document.createElement("div");
        card.className =
            "photo-card";
        const img =
            document.createElement("img");
        const url =
            URL.createObjectURL(
                photo.image
            );
        objectURLs.push(url);
        img.src = url;
        img.loading = "lazy";
        img.alt =
            "Photography";
        card.appendChild(img);
        gallery.appendChild(card);
    });
}
/* =========================================================
   RESEARCH
========================================================= */
function renderResearch(){
    const list =
        document.getElementById(
            "researchList"
        );
    list.innerHTML = "";
    if(data.documents.length === 0){
        list.innerHTML = `
            <div class="empty">
                No research documents added yet.
            </div>
        `;
        return;
    }
    data.documents.forEach(doc=>{
        const item =
            document.createElement("div");
        item.className =
            "research-item";
        const info =
            document.createElement("div");
        info.className =
            "research-info";
        const title =
            document.createElement("h3");
        title.textContent =
            doc.title;
        const description =
            document.createElement("p");
        description.textContent =
            doc.description ||
            "Research document";
        info.appendChild(title);
        info.appendChild(description);
        const link =
            document.createElement("a");
        const url =
            URL.createObjectURL(
                doc.file
            );
        objectURLs.push(url);
        link.href = url;
        link.target = "_blank";
        link.className =
            "research-link";
        link.textContent =
            "Open Document";
        item.appendChild(info);
        item.appendChild(link);
        list.appendChild(item);
    });
}
/* =========================================================
   NEWSPAPER
========================================================= */
function renderNews(){
    const list =
        document.getElementById(
            "newsList"
        );
    list.innerHTML = "";
    if(data.articles.length === 0){
        list.innerHTML = `
            <div
                class="empty"
                style="grid-column:1/-1;"
            >
                ${
                    data.newspaperHasPublishedArticle
                    ? "No articles are currently published."
                    : "Coming September 16"
                }
            </div>
        `;
        return;
    }
    data.articles.forEach(article=>{
        const card =
            document.createElement("article");
        card.className =
            "news-card";
        const date =
            document.createElement("div");
        date.className =
            "news-date";
        date.textContent =
            article.date;
        const title =
            document.createElement("h3");
        title.textContent =
            article.title;
        card.appendChild(date);
        card.appendChild(title);
        if(article.url){
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
            card.appendChild(link);
        }
        list.appendChild(card);
    });
}
/* =========================================================
   EDIT CODE
========================================================= */
function openCodeModal(){
    document
        .getElementById("codeModal")
        .classList.add("active");
    const input =
        document.getElementById(
            "editCode"
        );
    input.value = "";
    document
        .getElementById(
            "codeError"
        )
        .textContent = "";
    setTimeout(()=>{
        input.focus();
    },100);
}
function checkCode(){
    const entered =
        document
        .getElementById(
            "editCode"
        )
        .value
        .trim();
    if(entered === EDIT_CODE){
        closeModal("codeModal");
        document
            .getElementById(
                "editorModal"
            )
            .classList.add("active");
        populateEditor();
    }else{
        document
            .getElementById(
                "codeError"
            )
            .textContent =
                "Incorrect code. Try again.";
    }
}
/* =========================================================
   EDITOR
========================================================= */
function populateEditor(){
    document.getElementById(
        "editName"
    ).value =
        data.name;
    document.getElementById(
        "editBio"
    ).value =
        data.bio;
    updatePhotoStatus();
}
function showTab(tabId,button){
    document
        .querySelectorAll(".editor-tab")
        .forEach(tab=>{
            tab.style.display =
                "none";
        });
    document.getElementById(
        tabId
    ).style.display =
        "block";
    document
        .querySelectorAll(".tab")
        .forEach(tab=>{
            tab.classList.remove(
                "active"
            );
        });
    button.classList.add(
        "active"
    );
}
/* =========================================================
   SAVE HOME
========================================================= */
async function saveHome(){
    const name =
        document
        .getElementById(
            "editName"
        )
        .value
        .trim();
    const bio =
        document
        .getElementById(
            "editBio"
        )
        .value
        .trim();
    if(name){
        data.name = name;
        await put(
            "settings",
            {
                key:"name",
                value:name
            }
        );
    }
    data.bio = bio;
    await put(
        "settings",
        {
            key:"bio",
            value:bio
        }
    );
    const file =
        document
        .getElementById(
            "profileInput"
        )
        .files[0];
    if(file){
        try{
            const compressed =
                await compressImage(
                    file
                );
            data.profilePhoto =
                compressed;
            await put(
                "settings",
                {
                    key:"profilePhoto",
                    value:compressed
                }
            );
        }catch(error){
            alert(
                "The profile photo could not be processed."
            );
            return;
        }
    }
    document.getElementById(
        "profileInput"
    ).value = "";
    renderEverything();
    alert(
        "Your changes are now live."
    );
}
/* =========================================================
   COMPRESS IMAGE
========================================================= */
function compressImage(file){
    return new Promise(
        (resolve,reject)=>{
            const url =
                URL.createObjectURL(
                    file
                );
            const img =
                new Image();
            img.onload = ()=>{
                URL.revokeObjectURL(
                    url
                );
                const max =
                    1200;
                let width =
                    img.naturalWidth;
                let height =
                    img.naturalHeight;
                if(
                    width > max ||
                    height > max
                ){
                    if(width > height){
                        height =
                            Math.round(
                                height *
                                max /
                                width
                            );
                        width = max;
                    }else{
                        width =
                            Math.round(
                                width *
                                max /
                                height
                            );
                        height = max;
                    }
                }
                const canvas =
                    document.createElement(
                        "canvas"
                    );
                canvas.width =
                    width;
                canvas.height =
                    height;
                const ctx =
                    canvas.getContext(
                        "2d"
                    );
                ctx.drawImage(
                    img,
                    0,
                    0,
                    width,
                    height
                );
                canvas.toBlob(
                    blob=>{
                        if(blob){
                            resolve(blob);
                        }else{
                            reject(
                                new Error(
                                    "Compression failed."
                                )
                            );
                        }
                    },
                    "image/jpeg",
                    .55
                );
            };
            img.onerror = ()=>{
                URL.revokeObjectURL(
                    url
                );
                reject(
                    new Error(
                        "Image could not be read."
                    )
                );
            };
            img.src = url;
        }
    );
}
/* =========================================================
   ADD PHOTOS
========================================================= */
async function addPhotos(){
    const input =
        document.getElementById(
            "photoInput"
        );
    const files =
        Array.from(
            input.files
        );
    if(files.length === 0){
        alert(
            "Choose some photos first."
        );
        return;
    }
    if(
        data.photos.length +
        files.length >
        MAX_PHOTOS
    ){
        alert(
            "You can have a maximum of 25 photos."
        );
        return;
    }
    const status =
        document.getElementById(
            "photoStatus"
        );
    for(
        let i=0;
        i<files.length;
        i++
    ){
        status.textContent =
            `Compressing ${i+1} of ${files.length}...`;
        try{
            const compressed =
                await compressImage(
                    files[i]
                );
            const id =
                await add(
                    "photos",
                    {
                        image:compressed,
                        name:files[i].name
                    }
                );
            data.photos.push({
                id:id,
                image:compressed,
                name:files[i].name
            });
        }catch(error){
            console.error(error);
            alert(
                "One of the photos could not be processed."
            );
        }
    }
    input.value = "";
    renderEverything();
    status.textContent =
        `${data.photos.length} / ${MAX_PHOTOS} photos`;
    alert(
        "Photos added successfully."
    );
}
/* =========================================================
   PHOTO STATUS
========================================================= */
function updatePhotoStatus(){
    const status =
        document.getElementById(
            "photoStatus"
        );
    if(status){
        status.textContent =
            `${data.photos.length} / ${MAX_PHOTOS} photos`;
    }
}
/* =========================================================
   RESEARCH
========================================================= */
async function addResearch(){
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
    if(!title || !file){
        alert(
            "Enter a title and choose a document."
        );
        return;
    }
    const id =
        await add(
            "documents",
            {
                title:title,
                description:description,
                file:file,
                fileName:file.name
            }
        );
    data.documents.push({
        id:id,
        title:title,
        description:description,
        file:file,
        fileName:file.name
    });
    document.getElementById(
        "researchTitle"
    ).value = "";
    document.getElementById(
        "researchDescription"
    ).value = "";
    document.getElementById(
        "researchFile"
    ).value = "";
    renderEverything();
    alert(
        "Research document added."
    );
}
/* =========================================================
   NEWSPAPER
========================================================= */
async function addArticle(){
    const title =
        document
        .getElementById(
            "articleTitle"
        )
        .value
        .trim();
    const date =
        document
        .getElementById(
            "articleDate"
        )
        .value
        .trim();
    let url =
        document
        .getElementById(
            "articleURL"
        )
        .value
        .trim();
    if(!title || !url){
        alert(
            "Enter an article title and link."
        );
        return;
    }
    if(
        !/^https?:\/\//i.test(url)
    ){
        url =
            "https://" + url;
    }
    const id =
        await add(
            "articles",
            {
                title:title,
                date:date,
                url:url
            }
        );
    data.articles.push({
        id:id,
        title:title,
        date:date,
        url:url
    });
    data.newspaperHasPublishedArticle =
        true;
    await put(
        "settings",
        {
            key:
                "newspaperHasPublishedArticle",
            value:true
        }
    );
    document.getElementById(
        "articleTitle"
    ).value = "";
    document.getElementById(
        "articleDate"
    ).value = "";
    document.getElementById(
        "articleURL"
    ).value = "";
    renderEverything();
    alert(
        "Article published."
    );
}
/* =========================================================
   MODALS
========================================================= */
function closeModal(id){
    document
        .getElementById(id)
        .classList.remove(
            "active"
        );
}
document
    .querySelectorAll(".modal")
    .forEach(modal=>{
        modal.addEventListener(
            "click",
            event=>{
                if(
                    event.target ===
                    modal
                ){
                    modal.classList.remove(
                        "active"
                    );
                }
            }
        );
    });
document
    .getElementById(
        "editCode"
    )
    .addEventListener(
        "keydown",
        event=>{
            if(
                event.key ===
                "Enter"
            ){
                checkCode();
            }
        }
    );
/* =========================================================
   START
========================================================= */
loadData().catch(error=>{
    console.error(error);
    alert(
        "There was a problem loading your portfolio."
    );
});
</script>
</body>
</html>