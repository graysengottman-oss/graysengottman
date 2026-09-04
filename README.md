<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>My Portfolio</title>
<style>
:root{
    --bg:#0b0b0d;
    --card:#141416;
    --card2:#1b1b1f;
    --text:#f5f5f5;
    --muted:#a7a7ad;
    --line:#29292e;
    --accent:#ffffff;
    --danger:#ff5f56;
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
    font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Arial,sans-serif;
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
img{
    max-width:100%;
    display:block;
}
/* =========================
   NAVIGATION
========================= */
header{
    position:sticky;
    top:0;
    z-index:100;
    backdrop-filter:blur(18px);
    -webkit-backdrop-filter:blur(18px);
    background:rgba(11,11,13,.82);
    border-bottom:1px solid rgba(255,255,255,.08);
}
.nav{
    max-width:1150px;
    margin:auto;
    min-height:70px;
    padding:0 22px;
    display:flex;
    align-items:center;
    justify-content:space-between;
    gap:20px;
}
.logo{
    color:white;
    text-decoration:none;
    font-size:22px;
    font-weight:750;
    letter-spacing:-.6px;
}
.nav-links{
    display:flex;
    gap:7px;
    flex-wrap:wrap;
    justify-content:center;
}
.nav-links a{
    color:#bdbdc3;
    text-decoration:none;
    padding:9px 13px;
    border-radius:10px;
    font-size:14px;
    transition:.2s ease;
}
.nav-links a:hover{
    color:white;
    background:#1c1c20;
}
/* =========================
   GENERAL
========================= */
.container{
    max-width:1150px;
    margin:auto;
    padding:0 22px;
}
section{
    padding:90px 0;
}
.section-heading{
    margin-bottom:35px;
}
.section-heading h2{
    font-size:38px;
    line-height:1.1;
    letter-spacing:-1.5px;
    margin-bottom:10px;
}
.section-heading p{
    color:var(--muted);
    max-width:650px;
}
/* =========================
   HERO
========================= */
.hero{
    min-height:calc(100vh - 70px);
    display:flex;
    align-items:center;
}
.hero-grid{
    width:100%;
    display:grid;
    grid-template-columns:1.25fr .75fr;
    align-items:center;
    gap:70px;
}
.eyebrow{
    color:#9d9da5;
    text-transform:uppercase;
    letter-spacing:2px;
    font-size:12px;
    font-weight:700;
    margin-bottom:18px;
}
.hero h1{
    font-size:clamp(48px,8vw,92px);
    line-height:.95;
    letter-spacing:-5px;
    margin-bottom:25px;
}
.hero h1 span{
    color:#85858c;
}
.bio{
    max-width:650px;
    color:#b9b9bf;
    font-size:18px;
    line-height:1.75;
}
.hero-buttons{
    margin-top:30px;
    display:flex;
    gap:12px;
    flex-wrap:wrap;
}
.primary-btn,
.secondary-btn{
    border-radius:12px;
    padding:12px 18px;
    border:1px solid var(--line);
    transition:.2s ease;
}
.primary-btn{
    background:white;
    color:#080808;
    border-color:white;
    font-weight:700;
}
.primary-btn:hover{
    transform:translateY(-2px);
    opacity:.9;
}
.secondary-btn{
    background:#171719;
    color:white;
}
.secondary-btn:hover{
    background:#222226;
}
.profile-wrap{
    display:flex;
    justify-content:center;
}
.profile-photo{
    width:min(340px,75vw);
    aspect-ratio:1;
    object-fit:cover;
    border-radius:28px;
    border:1px solid #303035;
    background:#161619;
    box-shadow:0 30px 80px rgba(0,0,0,.45);
}
.profile-placeholder{
    width:min(340px,75vw);
    aspect-ratio:1;
    border-radius:28px;
    border:1px solid #303035;
    background:linear-gradient(145deg,#19191d,#101012);
    display:flex;
    align-items:center;
    justify-content:center;
    color:#6e6e75;
    text-align:center;
    padding:30px;
}
/* =========================
   CARDS
========================= */
.card{
    background:var(--card);
    border:1px solid var(--line);
    border-radius:20px;
    padding:25px;
}
.card:hover{
    border-color:#38383e;
}
/* =========================
   PHOTOGRAPHY
========================= */
.photo-grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:18px;
}
.photo-card{
    position:relative;
    overflow:hidden;
    border-radius:18px;
    background:#151518;
    border:1px solid #27272c;
    aspect-ratio:4/3;
}
.photo-card img{
    width:100%;
    height:100%;
    object-fit:cover;
    transition:transform .45s ease;
}
.photo-card:hover img{
    transform:scale(1.04);
}
/* =========================
   RESEARCH
========================= */
.research-list{
    display:grid;
    gap:15px;
}
.research-item{
    display:flex;
    align-items:center;
    justify-content:space-between;
    gap:20px;
    padding:20px;
    background:var(--card);
    border:1px solid var(--line);
    border-radius:16px;
}
.research-info h3{
    margin-bottom:4px;
    font-size:18px;
}
.research-info p{
    color:var(--muted);
    font-size:14px;
}
.research-link{
    flex-shrink:0;
    color:white;
    text-decoration:none;
    padding:9px 13px;
    border:1px solid #36363b;
    border-radius:9px;
    font-size:13px;
}
.research-link:hover{
    background:#202024;
}
/* =========================
   NEWSPAPER
========================= */
.news-grid{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:18px;
}
.news-card{
    background:var(--card);
    border:1px solid var(--line);
    border-radius:20px;
    padding:25px;
}
.news-date{
    color:#818189;
    font-size:12px;
    text-transform:uppercase;
    letter-spacing:1px;
    margin-bottom:10px;
}
.news-card h3{
    font-size:23px;
    margin-bottom:12px;
}
.news-card a{
    display:inline-block;
    margin-top:15px;
    color:white;
    text-decoration:none;
    border-bottom:1px solid #777;
}
/* =========================
   EMPTY STATE
========================= */
.empty{
    padding:45px 25px;
    text-align:center;
    border:1px dashed #333339;
    border-radius:18px;
    color:#77777f;
}
/* =========================
   FOOTER
========================= */
footer{
    border-top:1px solid var(--line);
    padding:30px 0;
    color:#707078;
    font-size:13px;
}
.footer-inner{
    display:flex;
    justify-content:space-between;
    gap:20px;
}
/* =========================
   EDIT BUTTON
========================= */
.edit-trigger{
    position:fixed;
    right:20px;
    bottom:20px;
    z-index:150;
    width:52px;
    height:52px;
    border-radius:50%;
    border:1px solid #3b3b40;
    background:#18181b;
    color:white;
    box-shadow:0 10px 35px rgba(0,0,0,.4);
    font-size:19px;
}
.edit-trigger:hover{
    background:#25252a;
}
/* =========================
   MODAL
========================= */
.modal{
    position:fixed;
    inset:0;
    z-index:200;
    background:rgba(0,0,0,.72);
    backdrop-filter:blur(12px);
    -webkit-backdrop-filter:blur(12px);
    display:none;
    align-items:center;
    justify-content:center;
    padding:20px;
}
.modal.active{
    display:flex;
}
.modal-box{
    width:min(700px,100%);
    max-height:90vh;
    overflow:auto;
    background:#111113;
    border:1px solid #303035;
    border-radius:22px;
    padding:28px;
    box-shadow:0 30px 100px rgba(0,0,0,.65);
}
.modal-header{
    display:flex;
    justify-content:space-between;
    align-items:center;
    gap:20px;
    margin-bottom:25px;
}
.modal-header h2{
    font-size:24px;
}
.close{
    width:36px;
    height:36px;
    border-radius:9px;
    border:1px solid #303035;
    background:#1b1b1e;
    color:white;
}
.close:hover{
    background:#27272c;
}
/* =========================
   TABS
========================= */
.tabs{
    display:flex;
    gap:7px;
    overflow:auto;
    padding-bottom:3px;
    margin-bottom:25px;
}
.tab{
    white-space:nowrap;
    padding:9px 13px;
    border-radius:9px;
    border:1px solid #303035;
    background:#171719;
    color:#aaaab0;
}
.tab.active{
    background:white;
    color:black;
    border-color:white;
}
/* =========================
   FORMS
========================= */
.form-group{
    margin-bottom:18px;
}
.form-group label{
    display:block;
    font-size:13px;
    font-weight:650;
    color:#d0d0d4;
    margin-bottom:8px;
}
input,
textarea{
    width:100%;
    border:1px solid #303035;
    background:#18181b;
    color:white;
    border-radius:11px;
    padding:12px 13px;
    outline:none;
}
input:focus,
textarea:focus{
    border-color:#65656d;
}
textarea{
    min-height:130px;
    resize:vertical;
}
input[type="file"]{
    padding:10px;
}
.form-actions{
    display:flex;
    justify-content:flex-end;
    gap:10px;
    margin-top:24px;
    flex-wrap:wrap;
}
.save-btn{
    background:white;
    color:black;
    border:0;
    border-radius:10px;
    padding:11px 17px;
    font-weight:700;
}
.cancel-btn{
    background:#1a1a1d;
    color:white;
    border:1px solid #303035;
    border-radius:10px;
    padding:11px 17px;
}
.status{
    color:#85858c;
    font-size:13px;
    margin-top:10px;
}
.warning{
    padding:13px;
    background:#1b1712;
    border:1px solid #493b27;
    color:#c8b28a;
    border-radius:10px;
    font-size:13px;
    margin-bottom:18px;
}
/* =========================
   MOBILE
========================= */
@media(max-width:800px){
    .nav{
        min-height:auto;
        padding:15px 18px;
        flex-direction:column;
    }
    .nav-links{
        width:100%;
        overflow-x:auto;
        justify-content:flex-start;
    }
    section{
        padding:65px 0;
    }
    .hero{
        min-height:auto;
        padding-top:70px;
    }
    .hero-grid{
        grid-template-columns:1fr;
        gap:45px;
    }
    .hero h1{
        letter-spacing:-3px;
    }
    .profile-wrap{
        order:-1;
    }
    .photo-grid{
        grid-template-columns:repeat(2,1fr);
    }
    .news-grid{
        grid-template-columns:1fr;
    }
    .research-item{
        align-items:flex-start;
        flex-direction:column;
    }
    .footer-inner{
        flex-direction:column;
    }
}
@media(max-width:480px){
    .photo-grid{
        grid-template-columns:1fr;
    }
    .section-heading h2{
        font-size:31px;
    }
    .hero h1{
        font-size:50px;
    }
}
</style>
</head>
<body>
<header>
    <nav class="nav">
        <a href="#home" class="logo" id="navLogo">Portfolio</a>
        <div class="nav-links">
            <a href="#home">Home</a>
            <a href="#photography">Photography</a>
            <a href="#research">Political Research</a>
            <a href="#newspaper">Newspaper</a>
        </div>
    </nav>
</header>
<main>
<!-- HOME -->
<section id="home" class="hero">
    <div class="container">
        <div class="hero-grid">
            <div>
                <div class="eyebrow">Portfolio</div>
                <h1 id="heroName">
                    Your Name
                </h1>
                <p class="bio" id="heroBio">
                    Welcome to my portfolio. This is where I share my photography,
                    research, writing, and projects.
                </p>
                <div class="hero-buttons">
                    <a href="#photography" class="primary-btn">
                        View Photography
                    </a>
                    <a href="#newspaper" class="secondary-btn">
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
<!-- PHOTOGRAPHY -->
<section id="photography">
    <div class="container">
        <div class="section-heading">
            <div class="eyebrow">Visual Work</div>
            <h2>Photography</h2>
            <p>
                A collection of photographs and visual work.
            </p>
        </div>
        <div id="photoGallery" class="photo-grid"></div>
    </div>
</section>
<!-- RESEARCH -->
<section id="research">
    <div class="container">
        <div class="section-heading">
            <div class="eyebrow">Research</div>
            <h2>Political Research</h2>
            <p>
                Research papers, documents, and projects.
            </p>
        </div>
        <div id="researchList" class="research-list"></div>
    </div>
</section>
<!-- NEWSPAPER -->
<section id="newspaper">
    <div class="container">
        <div class="section-heading">
            <div class="eyebrow">Writing</div>
            <h2>Newspaper</h2>
            <p>
                Articles and writing published through my newspaper work.
            </p>
        </div>
        <div id="newsList" class="news-grid"></div>
    </div>
</section>
</main>
<footer>
    <div class="container footer-inner">
        <div>© <span id="footerName">Portfolio</span></div>
        <div>Photography · Research · Writing</div>
    </div>
</footer>
<!-- EDIT BUTTON -->
<button class="edit-trigger" onclick="openCodeModal()" aria-label="Edit website">
    ✎
</button>
<!-- CODE MODAL -->
<div class="modal" id="codeModal">
    <div class="modal-box">
        <div class="modal-header">
            <h2>Enter Edit Code</h2>
            <button class="close" onclick="closeModal('codeModal')">×</button>
        </div>
        <div class="form-group">
            <label for="editCode">Edit Code</label>
            <input
                id="editCode"
                type="password"
                inputmode="numeric"
                placeholder="Enter code"
            >
        </div>
        <div id="codeError" class="status"></div>
        <div class="form-actions">
            <button class="cancel-btn" onclick="closeModal('codeModal')">
                Cancel
            </button>
            <button class="save-btn" onclick="checkCode()">
                Continue
            </button>
        </div>
    </div>
</div>
<!-- EDITOR MODAL -->
<div class="modal" id="editorModal">
    <div class="modal-box">
        <div class="modal-header">
            <h2>Edit Portfolio</h2>
            <button class="close" onclick="closeModal('editorModal')">×</button>
        </div>
        <div class="tabs">
            <button class="tab active" onclick="showTab('homeTab',this)">
                Home
            </button>
            <button class="tab" onclick="showTab('photoTab',this)">
                Photography
            </button>
            <button class="tab" onclick="showTab('researchTab',this)">
                Research
            </button>
            <button class="tab" onclick="showTab('newsTab',this)">
                Newspaper
            </button>
        </div>
        <!-- HOME EDITOR -->
        <div id="homeTab" class="editor-tab">
            <div class="form-group">
                <label for="editName">Name</label>
                <input id="editName" type="text">
            </div>
            <div class="form-group">
                <label for="editBio">Bio</label>
                <textarea id="editBio"></textarea>
            </div>
            <div class="form-group">
                <label for="profileInput">Profile Photo</label>
                <input
                    id="profileInput"
                    type="file"
                    accept="image/*"
                >
                <div class="status">
                    Your profile photo will automatically be compressed.
                </div>
            </div>
            <div class="form-actions">
                <button class="save-btn" onclick="saveHome()">
                    Save Changes
                </button>
            </div>
        </div>
        <!-- PHOTO EDITOR -->
        <div id="photoTab" class="editor-tab" style="display:none;">
            <div class="warning">
                You can store up to <strong>25 photos</strong>.
                Photos are automatically compressed before being stored on this device.
            </div>
            <div class="form-group">
                <label for="photoInput">
                    Add Photos
                </label>
                <input
                    id="photoInput"
                    type="file"
                    accept="image/*"
                    multiple
                >
                <div id="photoStatus" class="status">
                    0 / 25 photos
                </div>
            </div>
            <div class="form-actions">
                <button class="save-btn" onclick="addPhotos()">
                    Add Photos
                </button>
            </div>
        </div>
        <!-- RESEARCH EDITOR -->
        <div id="researchTab" class="editor-tab" style="display:none;">
            <div class="form-group">
                <label for="researchTitle">
                    Document Title
                </label>
                <input
                    id="researchTitle"
                    type="text"
                    placeholder="Research paper title"
                >
            </div>
            <div class="form-group">
                <label for="researchDescription">
                    Description
                </label>
                <textarea
                    id="researchDescription"
                    placeholder="Short description"
                ></textarea>
            </div>
            <div class="form-group">
                <label for="researchFile">
                    Document
                </label>
                <input
                    id="researchFile"
                    type="file"
                    accept=".pdf,.doc,.docx,.txt"
                >
            </div>
            <div class="form-actions">
                <button class="save-btn" onclick="addResearch()">
                    Add Document
                </button>
            </div>
        </div>
        <!-- NEWSPAPER EDITOR -->
        <div id="newsTab" class="editor-tab" style="display:none;">
            <div class="form-group">
                <label for="articleTitle">
                    Article Title
                </label>
                <input
                    id="articleTitle"
                    type="text"
                    placeholder="Article title"
                >
            </div>
            <div class="form-group">
                <label for="articleDate">
                    Date
                </label>
                <input
                    id="articleDate"
                    type="text"
                    placeholder="September 16, 2026"
                >
            </div>
            <div class="form-group">
                <label for="articleURL">
                    Article Link
                </label>
                <input
                    id="articleURL"
                    type="text"
                    placeholder="https://example.com"
                >
            </div>
            <div class="form-actions">
                <button class="save-btn" onclick="addArticle()">
                    Publish Article
                </button>
            </div>
        </div>
    </div>
</div>
<script>
/* ============================================================
   SETTINGS
============================================================ */
const EDIT_CODE = "4547";
const MAX_PHOTOS = 25;
const DB_NAME = "portfolioDatabase";
const DB_VERSION = 1;
let db;
let data = {
    name: "Your Name",
    bio: "Welcome to my portfolio. This is where I share my photography, research, writing, and projects.",
    profilePhoto: null,
    photos: [],
    documents: [],
    articles: [],
    newspaperHasPublishedArticle: false
};
let activeObjectURLs = [];
/* ============================================================
   INDEXED DB
============================================================ */
function openDatabase(){
    return new Promise((resolve,reject)=>{
        const request = indexedDB.open(DB_NAME,DB_VERSION);
        request.onupgradeneeded = function(event){
            const database = event.target.result;
            if(!database.objectStoreNames.contains("settings")){
                database.createObjectStore("settings",{keyPath:"key"});
            }
            if(!database.objectStoreNames.contains("photos")){
                database.createObjectStore("photos",{keyPath:"id",autoIncrement:true});
            }
            if(!database.objectStoreNames.contains("documents")){
                database.createObjectStore("documents",{keyPath:"id",autoIncrement:true});
            }
            if(!database.objectStoreNames.contains("articles")){
                database.createObjectStore("articles",{keyPath:"id",autoIncrement:true});
            }
        };
        request.onsuccess = function(event){
            db = event.target.result;
            resolve(db);
        };
        request.onerror = function(){
            reject(request.error);
        };
    });
}
function getStore(storeName,mode="readonly"){
    return db.transaction(storeName,mode).objectStore(storeName);
}
function getAll(storeName){
    return new Promise((resolve,reject)=>{
        const request = getStore(storeName).getAll();
        request.onsuccess = ()=>resolve(request.result);
        request.onerror = ()=>reject(request.error);
    });
}
function put(storeName,value){
    return new Promise((resolve,reject)=>{
        const request = getStore(storeName,"readwrite").put(value);
        request.onsuccess = ()=>resolve(request.result);
        request.onerror = ()=>reject(request.error);
    });
}
function add(storeName,value){
    return new Promise((resolve,reject)=>{
        const request = getStore(storeName,"readwrite").add(value);
        request.onsuccess = ()=>resolve(request.result);
        request.onerror = ()=>reject(request.error);
    });
}
function removeItem(storeName,id){
    return new Promise((resolve,reject)=>{
        const request = getStore(storeName,"readwrite").delete(id);
        request.onsuccess = ()=>resolve();
        request.onerror = ()=>reject(request.error);
    });
}
/* ============================================================
   LOAD DATA
============================================================ */
async function loadData(){
    await openDatabase();
    const settings = await getAll("settings");
    const savedPhotos = await getAll("photos");
    const savedDocuments = await getAll("documents");
    const savedArticles = await getAll("articles");
    for(const setting of settings){
        if(setting.key === "name"){
            data.name = setting.value;
        }
        if(setting.key === "bio"){
            data.bio = setting.value;
        }
        if(setting.key === "profilePhoto"){
            data.profilePhoto = setting.value;
        }
        if(setting.key === "newspaperHasPublishedArticle"){
            data.newspaperHasPublishedArticle = setting.value;
        }
    }
    data.photos = savedPhotos;
    data.documents = savedDocuments;
    data.articles = savedArticles;
    /*
        Automatically migrate the old localStorage version
        if it exists.
    */
    await migrateOldStorage();
    renderEverything();
}
/* ============================================================
   OLD STORAGE MIGRATION
============================================================ */
async function migrateOldStorage(){
    const old = localStorage.getItem("myMagazinePortfolio_v2");
    if(!old){
        return;
    }
    const alreadyMigrated = localStorage.getItem(
        "portfolioIndexedDBMigrated"
    );
    if(alreadyMigrated){
        return;
    }
    try{
        const oldData = JSON.parse(old);
        if(oldData.name){
            data.name = oldData.name;
            await put("settings",{
                key:"name",
                value:data.name
            });
        }
        if(oldData.bio){
            data.bio = oldData.bio;
            await put("settings",{
                key:"bio",
                value:data.bio
            });
        }
        if(oldData.newspaperHasPublishedArticle){
            data.newspaperHasPublishedArticle = true;
            await put("settings",{
                key:"newspaperHasPublishedArticle",
                value:true
            });
        }
        if(Array.isArray(oldData.photos)){
            for(const oldPhoto of oldData.photos){
                if(data.photos.length >= MAX_PHOTOS){
                    break;
                }
                if(oldPhoto.data){
                    try{
                        const blob = await compressDataURL(
                            oldPhoto.data
                        );
                        const id = await add("photos",{
                            image:blob,
                            name:oldPhoto.name || "Photo"
                        });
                        data.photos.push({
                            id,
                            image:blob,
                            name:oldPhoto.name || "Photo"
                        });
                    }catch(error){
                        console.log("Could not migrate photo.",error);
                    }
                }
            }
        }
        if(Array.isArray(oldData.documents)){
            for(const doc of oldData.documents){
                if(doc.data){
                    try{
                        const blob = dataURLToBlob(doc.data);
                        const id = await add("documents",{
                            title:doc.title || "Research Document",
                            description:doc.description || "",
                            file:blob,
                            fileName:doc.fileName || "document"
                        });
                        data.documents.push({
                            id,
                            title:doc.title || "Research Document",
                            description:doc.description || "",
                            file:blob,
                            fileName:doc.fileName || "document"
                        });
                    }catch(error){
                        console.log("Could not migrate document.",error);
                    }
                }
            }
        }
        if(Array.isArray(oldData.articles)){
            for(const article of oldData.articles){
                const id = await add("articles",{
                    title:article.title || "Article",
                    date:article.date || "",
                    url:article.url || ""
                });
                data.articles.push({
                    id,
                    title:article.title || "Article",
                    date:article.date || "",
                    url:article.url || ""
                });
            }
        }
        if(oldData.profilePhoto){
            try{
                const blob = await compressDataURL(
                    oldData.profilePhoto
                );
                data.profilePhoto = blob;
                await put("settings",{
                    key:"profilePhoto",
                    value:blob
                });
            }catch(error){
                console.log("Could not migrate profile photo.",error);
            }
        }
        localStorage.setItem(
            "portfolioIndexedDBMigrated",
            "true"
        );
    }catch(error){
        console.log("Migration failed:",error);
    }
}
/* ============================================================
   IMAGE COMPRESSION
============================================================ */
function dataURLToBlob(dataURL){
    const parts = dataURL.split(",");
    const mime = parts[0]
        .match(/:(.*?);/)[1];
    const binary = atob(parts[1]);
    const length = binary.length;
    const bytes = new Uint8Array(length);
    for(let i=0;i<length;i++){
        bytes[i] = binary.charCodeAt(i);
    }
    return new Blob([bytes],{type:mime});
}
async function compressDataURL(dataURL){
    const blob = dataURLToBlob(dataURL);
    return compressBlob(blob);
}
async function compressBlob(blob){
    return new Promise((resolve,reject)=>{
        const url = URL.createObjectURL(blob);
        const img = new Image();
        img.onload = function(){
            const maxDimension = 1200;
            let width = img.naturalWidth;
            let height = img.naturalHeight;
            if(width > maxDimension || height > maxDimension){
                if(width > height){
                    height =
                        Math.round(
                            height * maxDimension / width
                        );
                    width = maxDimension;
                }else{
                    width =
                        Math.round(
                            width * maxDimension / height
                        );
                    height = maxDimension;
                }
            }
            const canvas = document.createElement("canvas");
            canvas.width = width;
            canvas.height = height;
            const ctx = canvas.getContext("2d");
            ctx.drawImage(
                img,
                0,
                0,
                width,
                height
            );
            canvas.toBlob(
                function(compressed){
                    URL.revokeObjectURL(url);
                    if(!compressed){
                        reject(new Error("Compression failed."));
                        return;
                    }
                    resolve(compressed);
                },
                "image/jpeg",
                .55
            );
        };
        img.onerror = function(){
            URL.revokeObjectURL(url);
            reject(new Error("Image could not be read."));
        };
        img.src = url;
    });
}
/* ============================================================
   RENDER EVERYTHING
============================================================ */
function clearObjectURLs(){
    activeObjectURLs.forEach(url=>{
        URL.revokeObjectURL(url);
    });
    activeObjectURLs = [];
}
function renderEverything(){
    clearObjectURLs();
    document.getElementById("heroName").textContent =
        data.name;
    document.getElementById("navLogo").textContent =
        data.name || "Portfolio";
    document.getElementById("footerName").textContent =
        data.name || "Portfolio";
    document.getElementById("heroBio").textContent =
        data.bio;
    renderProfile();
    renderPhotos();
    renderResearch();
    renderNews();
    updatePhotoStatus();
}
/* ============================================================
   PROFILE
============================================================ */
function renderProfile(){
    const container =
        document.getElementById("profileContainer");
    container.innerHTML = "";
    if(data.profilePhoto){
        const img =
            document.createElement("img");
        const url =
            URL.createObjectURL(data.profilePhoto);
        activeObjectURLs.push(url);
        img.src = url;
        img.className = "profile-photo";
        img.alt = data.name + " profile photo";
        container.appendChild(img);
    }else{
        const placeholder =
            document.createElement("div");
        placeholder.className =
            "profile-placeholder";
        placeholder.textContent =
            "Add a profile photo from the Edit button.";
        container.appendChild(placeholder);
    }
}
/* ============================================================
   PHOTOS
============================================================ */
function renderPhotos(){
    const gallery =
        document.getElementById("photoGallery");
    gallery.innerHTML = "";
    if(data.photos.length === 0){
        gallery.innerHTML = `
            <div class="empty" style="grid-column:1/-1;">
                No photography has been added yet.
            </div>
        `;
        return;
    }
    data.photos.forEach(photo=>{
        const card =
            document.createElement("div");
        card.className = "photo-card";
        const img =
            document.createElement("img");
        const url =
            URL.createObjectURL(photo.image);
        activeObjectURLs.push(url);
        img.src = url;
        img.alt = "Photography";
        img.loading = "lazy";
        card.appendChild(img);
        /*
            No filename.
            No delete button.
            Just the photograph.
        */
        gallery.appendChild(card);
    });
}
/* ============================================================
   RESEARCH
============================================================ */
function renderResearch(){
    const list =
        document.getElementById("researchList");
    list.innerHTML = "";
    if(data.documents.length === 0){
        list.innerHTML = `
            <div class="empty">
                No research documents have been added yet.
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
            doc.description || "Research document";
        info.appendChild(title);
        info.appendChild(description);
        const link =
            document.createElement("a");
        const url =
            URL.createObjectURL(doc.file);
        activeObjectURLs.push(url);
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
/* ============================================================
   NEWSPAPER
============================================================ */
function renderNews(){
    const list =
        document.getElementById("newsList");
    list.innerHTML = "";
    if(data.articles.length === 0){
        list.innerHTML = `
            <div class="empty" style="grid-column:1/-1;">
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
/* ============================================================
   EDIT CODE
============================================================ */
function openCodeModal(){
    document
        .getElementById("codeModal")
        .classList.add("active");
    document
        .getElementById("editCode")
        .focus();
}
function checkCode(){
    const entered =
        document
        .getElementById("editCode")
        .value
        .trim();
    if(entered === EDIT_CODE){
        document
            .getElementById("codeModal")
            .classList.remove("active");
        document
            .getElementById("editorModal")
            .classList.add("active");
        populateEditor();
        document
            .getElementById("codeError")
            .textContent = "";
    }else{
        document
            .getElementById("codeError")
            .textContent =
            "Incorrect code.";
        document
            .getElementById("editCode")
            .select();
    }
}
/* ============================================================
   EDITOR
============================================================ */
function populateEditor(){
    document.getElementById("editName").value =
        data.name;
    document.getElementById("editBio").value =
        data.bio;
    updatePhotoStatus();
}
function showTab(tabId,button){
    document
        .querySelectorAll(".editor-tab")
        .forEach(tab=>{
            tab.style.display = "none";
        });
    document.getElementById(tabId).style.display =
        "block";
    document
        .querySelectorAll(".tab")
        .forEach(tab=>{
            tab.classList.remove("active");
        });
    button.classList.add("active");
}
/* ============================================================
   SAVE HOME
============================================================ */
async function saveHome(){
    const name =
        document
        .getElementById("editName")
        .value
        .trim();
    const bio =
        document
        .getElementById("editBio")
        .value
        .trim();
    if(name){
        data.name = name;
        await put("settings",{
            key:"name",
            value:name
        });
    }
    data.bio = bio;
    await put("settings",{
        key:"bio",
        value:bio
    });
    const file =
        document
        .getElementById("profileInput")
        .files[0];
    if(file){
        try{
            const compressed =
                await compressBlob(file);
            data.profilePhoto =
                compressed;
            await put("settings",{
                key:"profilePhoto",
                value:compressed
            });
        }catch(error){
            alert(
                "The profile photo could not be processed."
            );
            return;
        }
    }
    renderEverything();
    alert("Changes saved.");
    document
        .getElementById("profileInput")
        .value = "";
}
/* ============================================================
   PHOTOS
============================================================ */
async function addPhotos(){
    const input =
        document.getElementById("photoInput");
    const files =
        Array.from(input.files);
    if(files.length === 0){
        alert("Choose at least one photo.");
        return;
    }
    if(data.photos.length + files.length > MAX_PHOTOS){
        alert(
            `You can only have ${MAX_PHOTOS} photos. ` +
            `You currently have ${data.photos.length}.`
        );
        return;
    }
    const status =
        document.getElementById("photoStatus");
    for(let i=0;i<files.length;i++){
        status.textContent =
            `Compressing photo ${i+1} of ${files.length}...`;
        try{
            const compressed =
                await compressBlob(files[i]);
            const id =
                await add("photos",{
                    image:compressed,
                    name:files[i].name
                });
            data.photos.push({
                id:id,
                image:compressed,
                name:files[i].name
            });
        }catch(error){
            console.log(error);
            alert(
                `Could not process ${files[i].name}.`
            );
        }
    }
    input.value = "";
    renderEverything();
    status.textContent =
        `${data.photos.length} / ${MAX_PHOTOS} photos`;
    alert("Photos added.");
}
function updatePhotoStatus(){
    const status =
        document.getElementById("photoStatus");
    if(status){
        status.textContent =
            `${data.photos.length} / ${MAX_PHOTOS} photos`;
    }
}
/* ============================================================
   RESEARCH
============================================================ */
async function addResearch(){
    const title =
        document
        .getElementById("researchTitle")
        .value
        .trim();
    const description =
        document
        .getElementById("researchDescription")
        .value
        .trim();
    const file =
        document
        .getElementById("researchFile")
        .files[0];
    if(!title || !file){
        alert(
            "Please enter a title and choose a document."
        );
        return;
    }
    const id =
        await add("documents",{
            title:title,
            description:description,
            file:file,
            fileName:file.name
        });
    data.documents.push({
        id:id,
        title:title,
        description:description,
        file:file,
        fileName:file.name
    });
    document.getElementById("researchTitle").value =
        "";
    document.getElementById("researchDescription").value =
        "";
    document.getElementById("researchFile").value =
        "";
    renderEverything();
    alert("Research document added.");
}
/* ============================================================
   NEWSPAPER
============================================================ */
async function addArticle(){
    let title =
        document
        .getElementById("articleTitle")
        .value
        .trim();
    const date =
        document
        .getElementById("articleDate")
        .value
        .trim();
    let url =
        document
        .getElementById("articleURL")
        .value
        .trim();
    if(!title || !url){
        alert(
            "Please enter an article title and link."
        );
        return;
    }
    if(!/^https?:\/\//i.test(url)){
        url =
            "https://" + url;
    }
    const id =
        await add("articles",{
            title:title,
            date:date,
            url:url
        });
    data.articles.push({
        id:id,
        title:title,
        date:date,
        url:url
    });
    data.newspaperHasPublishedArticle =
        true;
    await put("settings",{
        key:"newspaperHasPublishedArticle",
        value:true
    });
    document.getElementById("articleTitle").value =
        "";
    document.getElementById("articleDate").value =
        "";
    document.getElementById("articleURL").value =
        "";
    renderEverything();
    alert("Article published.");
}
/* ============================================================
   MODALS
============================================================ */
function closeModal(id){
    document
        .getElementById(id)
        .classList.remove("active");
}
document.querySelectorAll(".modal").forEach(modal=>{
    modal.addEventListener("click",function(event){
        if(event.target === modal){
            modal.classList.remove("active");
        }
    });
});
document
    .getElementById("editCode")
    .addEventListener("keydown",function(event){
        if(event.key === "Enter"){
            checkCode();
        }
    });
/* ============================================================
   START
============================================================ */
loadData().catch(error=>{
    console.error(error);
    alert(
        "The portfolio could not load its saved data. " +
        "Try refreshing the page."
    );
});
</script>
</body>
</html>