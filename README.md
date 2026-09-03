<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>My Portfolio</title>

<style>
*{box-sizing:border-box}

:root{
--bg:#f2efe8;
--text:#111;
--muted:#777;
--line:#d4d0c8;
--white:#fff;
}

html{scroll-behavior:smooth}

body{
margin:0;
background:var(--bg);
color:var(--text);
font-family:Arial,Helvetica,sans-serif;
}

button,input,textarea{font:inherit}

button{cursor:pointer}

header{
position:sticky;
top:0;
z-index:100;
background:rgba(242,239,232,.94);
backdrop-filter:blur(18px);
border-bottom:1px solid var(--line);
}

.header{
max-width:1450px;
margin:auto;
padding:18px 30px;
display:flex;
align-items:center;
justify-content:space-between;
gap:20px;
}

.logo{
font-family:Georgia,serif;
font-size:25px;
}

nav{
display:flex;
align-items:center;
gap:5px;
flex-wrap:wrap;
}

nav button{
background:none;
border:0;
padding:9px 11px;
font-size:10px;
letter-spacing:1.5px;
text-transform:uppercase;
}

nav button:hover{text-decoration:underline}

.edit-button{
background:#111!important;
color:white;
}

main{
max-width:1450px;
margin:auto;
padding:50px 30px 100px;
}

.page{display:none}
.page.active{display:block}

.eyebrow{
font-size:10px;
letter-spacing:3px;
text-transform:uppercase;
color:var(--muted);
margin-bottom:15px;
}

h1,h2,h3{
font-family:Georgia,serif;
font-weight:normal;
}

h1{
font-size:clamp(60px,10vw,140px);
line-height:.86;
letter-spacing:-7px;
margin:0 0 35px;
}

h2{
font-size:clamp(50px,8vw,100px);
line-height:.9;
letter-spacing:-5px;
margin:0 0 40px;
}

.hero{
min-height:76vh;
display:grid;
grid-template-columns:1.1fr .9fr;
gap:70px;
align-items:center;
}

.bio{
max-width:650px;
font-size:18px;
line-height:1.7;
}

.profile{
aspect-ratio:4/5;
background:#ddd;
overflow:hidden;
}

.profile img{
width:100%;
height:100%;
object-fit:cover;
display:none;
}

.profile-empty{
height:100%;
display:flex;
align-items:center;
justify-content:center;
font-size:10px;
letter-spacing:2px;
text-transform:uppercase;
color:#777;
}

.gallery{
columns:3 280px;
column-gap:18px;
}

.photo{
break-inside:avoid;
margin-bottom:18px;
position:relative;
}

.photo img{
width:100%;
display:block;
}

.delete-photo{
display:none;
position:absolute;
right:12px;
top:12px;
width:36px;
height:36px;
border:0;
border-radius:50%;
background:rgba(0,0,0,.8);
color:#fff;
font-size:20px;
}

.editing .delete-photo{display:block}

.panel{
display:none;
border:1px solid #111;
padding:25px;
margin-bottom:40px;
}

.editing .panel{display:block}

.panel-title{
font-size:10px;
text-transform:uppercase;
letter-spacing:2px;
margin-bottom:20px;
}

input,textarea{
width:100%;
border:1px solid #aaa;
background:white;
padding:13px;
margin-bottom:15px;
outline:none;
}

textarea{
min-height:130px;
resize:vertical;
}

.primary{
background:#111;
color:#fff;
border:1px solid #111;
padding:12px 20px;
}

.secondary{
background:transparent;
color:#111;
border:1px solid #111;
padding:11px 18px;
}

.count{
font-size:11px;
color:#777;
margin-top:12px;
}

.article{
display:grid;
grid-template-columns:150px 1fr auto;
gap:30px;
align-items:center;
border-top:1px solid #111;
padding:30px 0;
}

.article-date{
font-size:10px;
letter-spacing:2px;
text-transform:uppercase;
color:#777;
}

.article-title{
font-family:Georgia,serif;
font-size:clamp(25px,4vw,45px);
}

.article-actions{
display:flex;
gap:8px;
flex-wrap:wrap;
}

.coming{
border-top:1px solid #111;
border-bottom:1px solid #111;
padding:70px 0;
}

.coming h3{
font-size:clamp(45px,8vw,100px);
letter-spacing:-5px;
margin:0;
}

.document{
display:flex;
justify-content:space-between;
align-items:center;
gap:20px;
border-top:1px solid #111;
padding:25px 0;
}

.document-title{
font-family:Georgia,serif;
font-size:25px;
}

footer{
max-width:1450px;
margin:auto;
border-top:1px solid #111;
padding:25px 30px;
display:flex;
justify-content:space-between;
font-size:10px;
text-transform:uppercase;
letter-spacing:2px;
}

.modal{
position:fixed;
inset:0;
z-index:500;
display:none;
align-items:center;
justify-content:center;
padding:20px;
background:rgba(0,0,0,.65);
}

.modal.open{display:flex}

.modal-box{
width:min(600px,100%);
max-height:90vh;
overflow:auto;
background:var(--bg);
padding:35px;
}

.modal-box h2{
font-size:55px;
margin-bottom:25px;
}

.error{
display:none;
color:#a00000;
font-size:12px;
margin-bottom:15px;
}

@media(max-width:750px){

.header{
padding:15px;
flex-wrap:wrap;
}

nav{
width:100%;
justify-content:space-between;
}

nav button{
font-size:8px;
padding:7px 4px;
}

main{
padding:35px 15px 70px;
}

.hero{
grid-template-columns:1fr;
gap:35px;
}

.profile{order:-1}

h1{
font-size:65px;
letter-spacing:-4px;
}

h2{
font-size:55px;
letter-spacing:-3px;
}

.gallery{
columns:2 130px;
column-gap:8px;
}

.photo{
margin-bottom:8px;
}

.article{
grid-template-columns:1fr;
gap:12px;
}

.document{
display:block;
}

footer{
padding:20px 15px;
display:block;
}
}
</style>
</head>

<body>

<header>
<div class="header">

<div class="logo" id="logo">Portfolio</div>

<nav>
<button onclick="showPage('home')">Home</button>
<button onclick="showPage('photography')">Photography</button>
<button onclick="showPage('research')">Research</button>
<button onclick="showPage('newspaper')">Newspaper</button>
<button class="edit-button" onclick="editButton()">Edit</button>
</nav>

</div>
</header>


<main>

<!-- HOME -->

<section id="home" class="page active">

<div class="hero">

<div>

<div class="eyebrow">
Photographer · Researcher · Writer
</div>

<h1 id="name">Your Name</h1>

<p class="bio" id="bio">
Welcome to my personal portfolio.
</p>

</div>

<div class="profile">

<img id="profilePhoto">

<div id="profileEmpty" class="profile-empty">
Profile Photo
</div>

</div>

</div>

<div class="panel">

<div class="panel-title">
Edit Home
</div>

<input id="nameInput" placeholder="Your name">

<textarea id="bioInput"
placeholder="Your biography"></textarea>

<input id="profileInput"
type="file"
accept="image/*">

<button class="primary" onclick="saveHome()">
Save Home
</button>

</div>

</section>


<!-- PHOTOGRAPHY -->

<section id="photography" class="page">

<div class="eyebrow">01 / Visual Archive</div>

<h2>Photography</h2>

<div class="panel">

<div class="panel-title">
Add Photography
</div>

<input
id="photoInput"
type="file"
accept="image/*"
multiple
>

<button class="primary"
onclick="uploadPhotos()">
Upload Photos
</button>

<div class="count" id="photoCount">
0 / 25 photos
</div>

</div>

<div id="gallery" class="gallery"></div>

</section>


<!-- RESEARCH -->

<section id="research" class="page">

<div class="eyebrow">
02 / Political Archive
</div>

<h2>Research</h2>

<div class="panel">

<div class="panel-title">
Add Research Document
</div>

<input
id="researchTitle"
placeholder="Document title"
>

<input
id="researchFile"
type="file"
accept=".pdf,.doc,.docx,.txt"
>

<button class="primary"
onclick="uploadResearch()">
Add Document
</button>

</div>

<div id="researchList"></div>

</section>


<!-- NEWSPAPER -->

<section id="newspaper" class="page">

<div class="eyebrow">
03 / School Newspaper
</div>

<h2>Articles</h2>

<div class="panel">

<div class="panel-title">
Add Article
</div>

<input
id="articleTitle"
placeholder="Article title"
>

<input
id="articleDate"
placeholder="September 20, 2026"
>

<input
id="articleURL"
placeholder="https://your-article.com"
>

<button class="primary"
onclick="addArticle()">
Publish Article
</button>

</div>


<div id="coming" class="coming">

<div class="eyebrow">
First edition
</div>

<h3>Coming September 16</h3>

<p>
School newspaper articles will appear here.
</p>

</div>

<div id="articleList"></div>

</section>

</main>


<footer>

<span id="footerName">
Your Name
</span>

<span>
Personal Archive
</span>

</footer>


<!-- EDIT CODE -->

<div id="codeModal" class="modal">

<div class="modal-box">

<div class="eyebrow">
Private Editor
</div>

<h2>Enter Code</h2>

<input
id="codeInput"
type="password"
maxlength="4"
inputmode="numeric"
placeholder="••••"
>

<div id="codeError" class="error">
Incorrect code.
</div>

<button class="primary"
onclick="checkCode()">
Enter
</button>

<button class="secondary"
onclick="closeCode()">
Cancel
</button>

</div>

</div>


<script>

/* =====================================================
   IMPORTANT SETTINGS
===================================================== */

/*
   PUT YOUR SUPABASE INFORMATION HERE.

   Do NOT change anything else until these are entered.
*/

const SUPABASE_URL =
"PASTE_YOUR_SUPABASE_URL_HERE";

const SUPABASE_KEY =
"PASTE_YOUR_SUPABASE_ANON_KEY_HERE";


/* YOUR EDIT CODE */

const EDIT_CODE = "4547";


/* MAXIMUM PHOTOS */

const MAX_PHOTOS = 25;


/* =====================================================
   STATE
===================================================== */

let editing = false;


/* =====================================================
   PAGE SWITCHING
===================================================== */

function showPage(id){

document
.querySelectorAll(".page")
.forEach(page=>{
page.classList.remove("active");
});

document
.getElementById(id)
.classList.add("active");

window.scrollTo({
top:0,
behavior:"smooth"
});

}


/* =====================================================
   EDIT BUTTON
===================================================== */

function editButton(){

if(editing){

editing=false;

document.body.classList.remove("editing");

return;

}

document
.getElementById("codeModal")
.classList.add("open");

document
.getElementById("codeInput")
.focus();

}


function checkCode(){

const code =
document
.getElementById("codeInput")
.value;

if(code === EDIT_CODE){

editing=true;

document.body.classList.add("editing");

closeCode();

}else{

document
.getElementById("codeError")
.style.display="block";

}

}


function closeCode(){

document
.getElementById("codeModal")
.classList.remove("open");

document
.getElementById("codeError")
.style.display="none";

document
.getElementById("codeInput")
.value="";

}


/* =====================================================
   SUPABASE REQUEST
===================================================== */

async function dbRequest(
endpoint,
options={}
){

if(
SUPABASE_URL.includes("PASTE_") ||
SUPABASE_KEY.includes("PASTE_")
){

throw new Error(
"Supabase has not been connected yet."
);

}

const response =
await fetch(
SUPABASE_URL +
"/rest/v1/" +
endpoint,
{

...options,

headers:{
"apikey":SUPABASE_KEY,
"Authorization":
"Bearer "+SUPABASE_KEY,
"Content-Type":
"application/json",
...(options.headers||{})
}

}
);

if(!response.ok){

const text =
await response.text();

throw new Error(text);

}

if(response.status===204)
return null;

return response.json();

}


/* =====================================================
   IMAGE COMPRESSION
===================================================== */

function compressImage(file){

return new Promise(
(resolve,reject)=>{

const reader =
new FileReader();

reader.onload =
event=>{

const image =
new Image();

image.onload=()=>{

let width=image.width;
let height=image.height;

const max=1800;

if(width>max || height>max){

if(width>height){

height =
height*max/width;

width=max;

}else{

width =
width*max/height;

height=max;

}

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

canvas.toBlob(
blob=>{

if(blob) resolve(blob);
else reject(
new Error("Compression failed")
);

},
"image/jpeg",
.82
);

};

image.onerror=reject;

image.src=event.target.result;

};

reader.onerror=reject;

reader.readAsDataURL(file);

});

}


/* =====================================================
   UPLOAD FILE TO SUPABASE STORAGE
===================================================== */

async function uploadStorage(
bucket,
path,
file
){

const response =
await fetch(

SUPABASE_URL +
"/storage/v1/object/" +
bucket +
"/" +
path,

{

method:"POST",

headers:{
"apikey":SUPABASE_KEY,
"Authorization":
"Bearer "+SUPABASE_KEY,
"Content-Type":
file.type || "application/octet-stream"
},

body:file

}

);

if(!response.ok){

throw new Error(
await response.text()
);

}

return response.json();

}


/* =====================================================
   PUBLIC FILE URL
===================================================== */

function publicFile(
bucket,
path
){

return (
SUPABASE_URL +
"/storage/v1/object/public/" +
bucket +
"/" +
path
);

}


/* =====================================================
   PHOTOGRAPHY
===================================================== */

async function uploadPhotos(){

if(!editing){

alert("Enter 4547 first.");

return;

}

const input =
document.getElementById("photoInput");

const files =
Array.from(input.files);

if(!files.length){

alert("Choose photos first.");

return;

}


const current =
await dbRequest(
"photos?select=id"
);

if(
current.length + files.length >
MAX_PHOTOS
){

alert(
"You can have a maximum of 25 photos."
);

return;

}


try{

for(const file of files){

const compressed =
await compressImage(file);

const filename =
Date.now()+"-"+Math.random()
.toString(36)
.substring(2)+".jpg";


await uploadStorage(
"photos",
filename,
compressed
);


await dbRequest(
"photos",
{

method:"POST",

body:JSON.stringify({

filename:filename,

url:publicFile(
"photos",
filename
),

created_at:
new Date().toISOString()

})

}
);

}

input.value="";

await loadPhotos();

alert("Photos published.");

}catch(error){

console.error(error);

alert(
"Could not upload photos. Check your storage setup."
);

}

}


/* =====================================================
   LOAD PHOTOS
===================================================== */

async function loadPhotos(){

try{

const photos =
await dbRequest(
"photos?select=*&order=created_at.desc"
);

const gallery =
document.getElementById("gallery");

gallery.innerHTML="";


photos.forEach(photo=>{

const card =
document.createElement("div");

card.className="photo";


const image =
document.createElement("img");

image.src=photo.url;

image.loading="lazy";


const deleteButton =
document.createElement("button");

deleteButton.className=
"delete-photo";

deleteButton.textContent="×";

deleteButton.onclick=()=>{
deletePhoto(photo);
};


card.appendChild(image);
card.appendChild(deleteButton);

gallery.appendChild(card);

});


document
.getElementById("photoCount")
.textContent=
photos.length+
" / "+
MAX_PHOTOS+
" photos";

}catch(error){

console.error(error);

}

}


/* =====================================================
   DELETE PHOTO
===================================================== */

async function deletePhoto(photo){

if(!editing)return;

if(
!confirm(
"Delete this photograph?"
)
)return;


try{

await dbRequest(
"photos?id=eq."+photo.id,
{
method:"DELETE"
}
);


await fetch(

SUPABASE_URL+
"/storage/v1/object/photos/"+
photo.filename,

{

method:"DELETE",

headers:{
"apikey":SUPABASE_KEY,
"Authorization":
"Bearer "+SUPABASE_KEY
}

}
);


loadPhotos();

}catch(error){

console.error(error);

alert("Could not delete photo.");

}

}


/* =====================================================
   HOME
===================================================== */

async function loadHome(){

try{

const data =
await dbRequest(
"site_settings?select=*&id=eq.1"
);

if(!data.length)return;

const settings=data[0];


document
.getElementById("name")
.textContent=
settings.name ||
"Your Name";


document
.getElementById("logo")
.textContent=
settings.name ||
"Portfolio";


document
.getElementById("footerName")
.textContent=
settings.name ||
"Your Name";


document
.getElementById("bio")
.textContent=
settings.bio ||
"Welcome to my personal portfolio.";


if(settings.profile_url){

const image =
document.getElementById(
"profilePhoto"
);

image.src=
settings.profile_url;

image.style.display="block";

document
.getElementById("profileEmpty")
.style.display="none";

}

}catch(error){

console.error(error);

}

}


async function saveHome(){

if(!editing)return;


const name =
document
.getElementById("nameInput")
.value.trim();


const bio =
document
.getElementById("bioInput")
.value.trim();


const file =
document
.getElementById("profileInput")
.files[0];


try{

let profileURL=null;


if(file){

const compressed =
await compressImage(file);

const filename=
"profile-"+Date.now()+".jpg";

await uploadStorage(
"photos",
filename,
compressed
);

profileURL=
publicFile(
"photos",
filename
);

}


const existing =
await dbRequest(
"site_settings?select=*&id=eq.1"
);


const object={

id:1,

name:name||"Your Name",

bio:
bio||
"Welcome to my personal portfolio."

};


if(profileURL)
object.profile_url=
profileURL;


if(existing.length){

await dbRequest(
"site_settings?id=eq.1",
{
method:"PATCH",
body:JSON.stringify(object)
}
);

}else{

await dbRequest(
"site_settings",
{
method:"POST",
body:JSON.stringify(object)
}
);

}


await loadHome();

alert("Home page updated.");

}catch(error){

console.error(error);

alert(
"Could not save your changes."
);

}

}


/* =====================================================
   ARTICLE SYSTEM
===================================================== */

async function addArticle(){

if(!editing){

alert("Enter 4547 first.");

return;

}


const title =
document
.getElementById("articleTitle")
.value.trim();


const date =
document
.getElementById("articleDate")
.value.trim();


const url =
document
.getElementById("articleURL")
.value.trim();


if(!title || !url){

alert(
"Enter an article title and link."
);

return;

}


try{

await dbRequest(
"articles",
{

method:"POST",

body:JSON.stringify({

title:title,

date:
date||"Published",

url:url,

created_at:
new Date().toISOString()

})

}
);


document
.getElementById("articleTitle")
.value="";

document
.getElementById("articleDate")
.value="";

document
.getElementById("articleURL")
.value="";


await loadArticles();

alert("Article published.");

}catch(error){

console.error(error);

alert(
"Could not publish article."
);

}

}


/* =====================================================
   LOAD ARTICLES
===================================================== */

async function loadArticles(){

try{

const articles =
await dbRequest(
"articles?select=*&order=created_at.desc"
);


const list =
document
.getElementById("articleList");

list.innerHTML="";


if(articles.length){

document
.getElementById("coming")
.style.display="none";

}else{

document
.getElementById("coming")
.style.display="block";

}


articles.forEach(article=>{

const row =
document.createElement("div");

row.className="article";


const date =
document.createElement("div");

date.className="article-date";

date.textContent=
article.date;


const title =
document.createElement("div");

title.className="article-title";

title.textContent=
article.title;


const actions =
document.createElement("div");

actions.className=
"article-actions";


const read =
document.createElement("a");

read.className=
"secondary";

read.textContent=
"Read Article";

read.href=
safeURL(article.url);

read.target="_blank";

read.rel=
"noopener noreferrer";


actions.appendChild(read);


if(editing){

const remove =
document.createElement("button");

remove.className=
"secondary";

remove.textContent=
"Delete";

remove.onclick=
()=>deleteArticle(article);

actions.appendChild(remove);

}


row.appendChild(date);
row.appendChild(title);
row.appendChild(actions);

list.appendChild(row);

});

}catch(error){

console.error(error);

}

}


async function deleteArticle(article){

if(
!confirm(
"Delete this article?"
)
)return;


await dbRequest(
"articles?id=eq."+article.id,
{
method:"DELETE"
}
);

loadArticles();

}


/* =====================================================
   RESEARCH
===================================================== */

async function uploadResearch(){

if(!editing){

alert("Enter 4547 first.");

return;

}


const title =
document
.getElementById("researchTitle")
.value.trim();


const file =
document
.getElementById("researchFile")
.files[0];


if(!title || !file){

alert(
"Enter a title and choose a file."
);

return;

}


try{

const filename=
Date.now()+"-"+file.name;


await uploadStorage(
"research",
filename,
file
);


await dbRequest(
"research",
{

method:"POST",

body:JSON.stringify({

title:title,

filename:filename,

created_at:
new Date().toISOString()

})

}
);


document
.getElementById("researchTitle")
.value="";

document
.getElementById("researchFile")
.value="";


loadResearch();

alert("Research document added.");

}catch(error){

console.error(error);

alert(
"Could not upload research."
);

}

}


/* =====================================================
   LOAD RESEARCH
===================================================== */

async function loadResearch(){

try{

const data =
await dbRequest(
"research?select=*&order=created_at.desc"
);


const list =
document
.getElementById("researchList");

list.innerHTML="";


data.forEach(item=>{

const row =
document.createElement("div");

row.className="document";


const title =
document.createElement("div");

title.className="document-title";

title.textContent=
item.title;


const actions =
document.createElement("div");


const open =
document.createElement("a");

open.className="secondary";

open.textContent="Open";

open.href=
publicFile(
"research",
item.filename
);

open.target="_blank";


actions.appendChild(open);


if(editing){

const del =
document.createElement("button");

del.className="secondary";

del.textContent="Delete";

del.onclick=
()=>deleteResearch(item);

actions.appendChild(del);

}


row.appendChild(title);
row.appendChild(actions);

list.appendChild(row);

});

}catch(error){

console.error(error);

}

}


async function deleteResearch(item){

if(
!confirm(
"Delete this document?"
)
)return;


await dbRequest(
"research?id=eq."+item.id,
{
method:"DELETE"
}
);


await fetch(

SUPABASE_URL+
"/storage/v1/object/research/"+
item.filename,

{

method:"DELETE",

headers:{
"apikey":SUPABASE_KEY,
"Authorization":
"Bearer "+SUPABASE_KEY
}

}
);


loadResearch();

}


/* =====================================================
   SAFE ARTICLE LINKS
===================================================== */

function safeURL(url){

try{

const u=new URL(url);

if(
u.protocol!=="https:" &&
u.protocol!=="http:"
){

return "#";

}

return u.href;

}catch{

return "#";

}

}


/* =====================================================
   REFRESH EDITABLE LISTS
===================================================== */

function refresh(){

loadHome();

loadPhotos();

loadArticles();

loadResearch();

}


/* =====================================================
   START WEBSITE
===================================================== */

window.addEventListener(
"DOMContentLoaded",
()=>{

refresh();

}
);


/* =====================================================
   ENTER KEY FOR CODE
===================================================== */

document
.getElementById("codeInput")
.addEventListener(
"keydown",
event=>{

if(event.key==="Enter")
checkCode();

}
);

</script>

</body>
</html>