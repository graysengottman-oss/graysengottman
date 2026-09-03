<!DOCTYPE html>
<html lang="en">

<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Portfolio</title>

<style>

* {
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    margin: 0;
    background: #f3f0e9;
    color: #111;
    font-family: Arial, Helvetica, sans-serif;
}

header {
    position: sticky;
    top: 0;
    z-index: 100;
    background: rgba(243,240,233,.94);
    backdrop-filter: blur(15px);
    border-bottom: 1px solid #ccc;
}

.header {
    max-width: 1400px;
    margin: auto;
    padding: 18px 30px;

    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
}

.logo {
    font-family: Georgia, serif;
    font-size: 25px;
}

nav {
    display: flex;
    gap: 8px;
    align-items: center;
}

nav button {
    border: 0;
    background: transparent;
    padding: 9px 12px;
    cursor: pointer;

    font-size: 11px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
}

.edit {
    background: #111;
    color: white;
}

main {
    max-width: 1400px;
    margin: auto;
    padding: 50px 30px 100px;
}

.page {
    display: none;
}

.page.active {
    display: block;
}

.eyebrow {
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 3px;
    color: #777;
    margin-bottom: 15px;
}

h1 {
    font-family: Georgia, serif;
    font-size: clamp(60px, 9vw, 130px);
    line-height: .88;
    font-weight: normal;
    letter-spacing: -6px;
    margin: 0 0 35px;
}

h2 {
    font-family: Georgia, serif;
    font-size: clamp(50px, 7vw, 90px);
    font-weight: normal;
    letter-spacing: -4px;
}

.bio {
    max-width: 650px;
    font-size: 18px;
    line-height: 1.7;
}

.hero {
    min-height: 75vh;

    display: grid;
    grid-template-columns: 1.1fr .9fr;
    gap: 60px;
    align-items: center;
}

.profile {
    aspect-ratio: 4 / 5;
    background: #ddd;
    overflow: hidden;
}

.profile img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.gallery {
    columns: 3 280px;
    column-gap: 18px;
}

.photo {
    break-inside: avoid;
    margin-bottom: 18px;
    position: relative;
}

.photo img {
    width: 100%;
    display: block;
}

.delete-photo {
    position: absolute;
    top: 10px;
    right: 10px;

    width: 35px;
    height: 35px;

    border: 0;
    border-radius: 50%;

    background: rgba(0,0,0,.8);
    color: white;

    cursor: pointer;
}

.editing .delete-photo {
    display: block;
}

.delete-photo {
    display: none;
}

.panel {
    display: none;

    border: 1px solid #111;
    padding: 25px;
    margin-bottom: 35px;
}

.editing .panel {
    display: block;
}

input,
textarea {
    width: 100%;
    padding: 13px;

    border: 1px solid #aaa;
    background: white;

    margin-bottom: 15px;
}

textarea {
    min-height: 130px;
}

.primary {
    border: 1px solid #111;
    background: #111;
    color: white;
    padding: 12px 18px;
    cursor: pointer;
}

.secondary {
    border: 1px solid #111;
    background: transparent;
    padding: 12px 18px;
    cursor: pointer;
}

.article {
    border-top: 1px solid #111;

    padding: 30px 0;

    display: grid;
    grid-template-columns: 150px 1fr auto;

    gap: 25px;
    align-items: center;
}

.article-title {
    font-family: Georgia, serif;
    font-size: 35px;
}

.date {
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 2px;
    color: #777;
}

.coming {
    border-top: 1px solid #111;
    border-bottom: 1px solid #111;

    padding: 70px 0;
}

.coming h3 {
    font-family: Georgia, serif;
    font-size: clamp(45px,7vw,90px);
    font-weight: normal;
    margin: 0;
}

.document {
    border-top: 1px solid #111;
    padding: 25px 0;

    display: flex;
    justify-content: space-between;
    gap: 20px;
}

.modal {
    display: none;

    position: fixed;
    inset: 0;

    z-index: 500;

    background: rgba(0,0,0,.65);

    align-items: center;
    justify-content: center;

    padding: 20px;
}

.modal.active {
    display: flex;
}

.modal-box {
    background: #f3f0e9;

    width: min(550px,100%);

    padding: 35px;
}

.modal-box h2 {
    font-size: 50px;
    margin-top: 0;
}

footer {
    max-width: 1400px;
    margin: auto;

    border-top: 1px solid #111;

    padding: 25px 30px;

    display: flex;
    justify-content: space-between;

    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 2px;
}

@media(max-width:750px) {

    .header {
        padding: 15px;
        flex-wrap: wrap;
    }

    nav {
        width: 100%;
        justify-content: space-between;
    }

    nav button {
        font-size: 9px;
        padding: 7px 4px;
    }

    main {
        padding: 35px 15px 70px;
    }

    .hero {
        grid-template-columns: 1fr;
        gap: 35px;
    }

    .profile {
        order: -1;
    }

    h1 {
        font-size: 65px;
    }

    .gallery {
        columns: 2 130px;
        column-gap: 8px;
    }

    .photo {
        margin-bottom: 8px;
    }

    .article {
        grid-template-columns: 1fr;
    }

    .article-title {
        font-size: 30px;
    }

    footer {
        padding: 20px 15px;
    }
}

</style>
</head>


<body>


<header>

<div class="header">

<div class="logo" id="logo">
Portfolio
</div>

<nav>

<button onclick="page('home')">
Home
</button>

<button onclick="page('photography')">
Photography
</button>

<button onclick="page('research')">
Research
</button>

<button onclick="page('newspaper')">
Newspaper
</button>

<button class="edit" onclick="openEditor()">
Edit
</button>

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

<h1 id="name">
Your Name
</h1>

<p class="bio" id="bio">
Welcome to my personal portfolio.
</p>

</div>


<div class="profile">

<img id="profilePhoto"
style="display:none">

</div>

</div>

</section>



<!-- PHOTOGRAPHY -->

<section id="photography" class="page">

<div class="eyebrow">
01 / Visual Archive
</div>

<h2>
Photography
</h2>


<div class="panel">

<h3>
Add Photography
</h3>

<p>
Up to 25 photographs.
</p>

<input
id="photoUpload"
type="file"
accept="image/*"
multiple
>

<button
class="primary"
onclick="uploadPhotos()">

Upload Photos

</button>

</div>


<div id="gallery"
class="gallery">

</div>

</section>



<!-- RESEARCH -->

<section id="research" class="page">

<div class="eyebrow">
02 / Political Archive
</div>

<h2>
Research
</h2>


<div class="panel">

<h3>
Add Research
</h3>

<p>
Research documents should be kept private rather than placed in the public GitHub Pages repository.
</p>

</div>


<div class="document">

Political research archive

<span>
Private
</span>

</div>

</section>



<!-- NEWSPAPER -->

<section id="newspaper" class="page">

<div class="eyebrow">
03 / School Newspaper
</div>

<h2>
Articles
</h2>


<div class="panel">

<h3>
Add Article
</h3>


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
placeholder="https://..."
>


<button
class="primary"
onclick="addArticle()">

Publish Article

</button>

</div>


<div
id="coming"
class="coming">

<div class="eyebrow">
First edition
</div>

<h3>
Coming September 16
</h3>

<p>
School newspaper articles will appear here.
</p>

</div>


<div id="articles">

</div>

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



<!-- CODE MODAL -->

<div
id="codeModal"
class="modal">

<div class="modal-box">

<div class="eyebrow">
Private Editor
</div>

<h2>
Edit
</h2>

<input
id="code"
type="password"
maxlength="4"
inputmode="numeric"
placeholder="Enter 4 digit code"
>

<p
id="error"
style="display:none;color:#a00">

Incorrect code.

</p>

<button
class="primary"
onclick="checkCode()">

Continue

</button>

<button
class="secondary"
onclick="closeModal()">

Cancel

</button>

</div>

</div>



<script>

/* ======================================================
   GITHUB SETTINGS
====================================================== */

const GITHUB_OWNER =
"YOUR-GITHUB-USERNAME";

const GITHUB_REPO =
"YOUR-REPOSITORY";

const GITHUB_BRANCH =
"main";


/* YOUR EDIT CODE */

const EDIT_CODE =
"4547";


/* PHOTO LIMIT */

const MAX_PHOTOS =
25;


/* ======================================================
   NAVIGATION
====================================================== */

function page(name) {

document
.querySelectorAll(".page")
.forEach(p =>
p.classList.remove("active")
);

document
.getElementById(name)
.classList.add("active");

window.scrollTo({
top:0,
behavior:"smooth"
});

}


/* ======================================================
   EDITING
====================================================== */

let editing =
false;


function openEditor() {

if(editing) {

editing = false;

document.body
.classList.remove("editing");

return;

}

document
.getElementById("codeModal")
.classList.add("active");

document
.getElementById("code")
.focus();

}


function checkCode() {

const entered =
document
.getElementById("code")
.value;

if(entered === EDIT_CODE) {

editing = true;

document.body
.classList.add("editing");

closeModal();

} else {

document
.getElementById("error")
.style.display =
"block";

}

}


function closeModal() {

document
.getElementById("codeModal")
.classList.remove("active");

}


/* ======================================================
   GITHUB API
====================================================== */

/*

IMPORTANT:

Never put a GitHub access token here.

The website will ask the owner for authorization
when an edit needs to be made.

*/


async function githubRequest(
url,
options={}
) {

const token =
sessionStorage.getItem(
"github_token"
);

if(!token) {

const newToken =
prompt(
"Enter your GitHub access token:"
);

if(!newToken) {

throw new Error(
"GitHub authorization required."
);

}

sessionStorage.setItem(
"github_token",
newToken
);

return githubRequest(
url,
options
);

}


options.headers = {

...(options.headers || {}),

"Authorization":
"Bearer " + token,

"Accept":
"application/vnd.github+json",

"X-GitHub-Api-Version":
"2022-11-28"

};


const response =
await fetch(
url,
options
);


if(response.status === 401) {

sessionStorage.removeItem(
"github_token"
);

throw new Error(
"GitHub authorization expired."
);

}


if(!response.ok) {

throw new Error(
"GitHub request failed."
);

}


return response.json();

}


/* ======================================================
   GET FILE
====================================================== */

async function getGithubFile(
path
) {

const url =
`https://api.github.com/repos/${GITHUB_OWNER}/${GITHUB_REPO}/contents/${path}?ref=${GITHUB_BRANCH}`;

return githubRequest(url);

}


/* ======================================================
   SAVE FILE
====================================================== */

async function saveGithubFile(
path,
content,
message,
sha=null
) {

const url =
`https://api.github.com/repos/${GITHUB_OWNER}/${GITHUB_REPO}/contents/${path}`;


const body = {

message: message,

content: content,

branch: GITHUB_BRANCH

};


if(sha) {

body.sha =
sha;

}


return githubRequest(
url,
{
method:"PUT",

headers:{
"Content-Type":
"application/json"
},

body:
JSON.stringify(body)

}
);

}


/* ======================================================
   BASE64
====================================================== */

function fileToBase64(file) {

return new Promise(
(resolve,reject)=> {

const reader =
new FileReader();

reader.onload =
() => {

const result =
reader.result;

resolve(
result.split(",")[1]
);

};

reader.onerror =
reject;

reader.readAsDataURL(file);

});

}


/* ======================================================
   UPLOAD PHOTOS
====================================================== */

async function uploadPhotos() {

if(!editing) {

alert(
"Enter the edit code first."
);

return;

}


const files =
Array.from(
document
.getElementById("photoUpload")
.files
);


if(files.length === 0) {

alert(
"Choose at least one photo."
);

return;

}


if(files.length > MAX_PHOTOS) {

alert(
"You can upload up to 25 photos at a time."
);

return;

}


alert(
"GitHub will now be used to publish your photographs."
);


/*

For a production version, photographs should
be stored in an external image CDN or Git LFS
rather than putting many large originals directly
into the repository.

This starter system stores optimized JPEGs.

*/


for(const file of files) {

const compressed =
await compressImage(
file
);

const base64 =
await fileToBase64(
compressed
);


const filename =
"photo-" +
Date.now() +
"-" +
Math.random()
.toString(36)
.substring(2,8) +
".jpg";


await saveGithubFile(

"photos/" +
filename,

base64,

"Add photography " +
filename

);

}


alert(
"Photos published. Refresh the website to see them."
);

}


/* ======================================================
   IMAGE COMPRESSION
====================================================== */

function compressImage(file) {

return new Promise(
(resolve,reject)=> {

const reader =
new FileReader();

reader.onload =
event => {

const img =
new Image();

img.onload =
() => {

let width =
img.width;

let height =
img.height;

const max =
1800;


if(width > max ||
height > max) {

if(width > height) {

height =
height *
max /
width;

width =
max;

} else {

width =
width *
max /
height;

height =
max;

}

}


const canvas =
document
.createElement("canvas");

canvas.width =
Math.round(width);

canvas.height =
Math.round(height);


const ctx =
canvas.getContext("2d");

ctx.drawImage(
img,
0,
0,
canvas.width,
canvas.height
);


canvas.toBlob(
blob =>
resolve(blob),
"image/jpeg",
.82
);

};


img.onerror =
reject;

img.src =
event.target.result;

};


reader.onerror =
reject;

reader.readAsDataURL(file);

});

}


/* ======================================================
   LOAD PUBLIC PHOTOS
====================================================== */

async function loadPhotos() {

try {

const url =
`https://api.github.com/repos/${GITHUB_OWNER}/${GITHUB_REPO}/contents/photos?ref=${GITHUB_BRANCH}`;

const response =
await fetch(url);

if(!response.ok)
return;

const files =
await response.json();


const gallery =
document
.getElementById("gallery");

gallery.innerHTML = "";


for(const file of files) {

if(!file.name
.match(/\.(jpg|jpeg|png|webp)$/i))
continue;


const card =
document
.createElement("div");

card.className =
"photo";


const image =
document
.createElement("img");

image.loading =
"lazy";

image.src =
file.download_url;

image.alt =
"Photography";


const deleteButton =
document
.createElement("button");

deleteButton.className =
"delete-photo";

deleteButton.textContent =
"×";


deleteButton.onclick =
() =>
deletePhoto(
file.path,
file.sha
);


card.appendChild(
image
);

card.appendChild(
deleteButton
);

gallery.appendChild(
card
);

}

} catch(error) {

console.error(error);

}

}


/* ======================================================
   DELETE PHOTO
====================================================== */

async function deletePhoto(
path,
sha
) {

if(!editing)
return;


if(!confirm(
"Delete this photograph?"
))
return;


await githubRequest(

`https://api.github.com/repos/${GITHUB_OWNER}/${GITHUB_REPO}/contents/${path}`,

{

method:"DELETE",

headers:{
"Content-Type":
"application/json"
},

body:
JSON.stringify({

message:
"Delete photograph",

sha:
sha,

branch:
GITHUB_BRANCH

})

);


loadPhotos();

}


/* ======================================================
   ARTICLES
====================================================== */

async function addArticle() {

if(!editing) {

alert(
"Enter the edit code first."
);

return;

}


const title =
document
.getElementById("articleTitle")
.value
.trim();


const date =
document
.getElementById("articleDate")
.value
.trim();


const url =
document
.getElementById("articleURL")
.value
.trim();


if(!title || !url) {

alert(
"Enter a title and article link."
);

return;

}


const article = {

title:title,

date:
date || "Published",

url:url

};


const filename =
"article-" +
Date.now() +
".json";


const encoded =
btoa(
unescape(
encodeURIComponent(
JSON.stringify(
article,
null,
2
)
)
)
);


await saveGithubFile(

"articles/" +
filename,

encoded,

"Add newspaper article"

);


document
.getElementById("articleTitle")
.value = "";

document
.getElementById("articleDate")
.value = "";

document
.getElementById("articleURL")
.value = "";


alert(
"Article published."
);


loadArticles();

}


/* ======================================================
   LOAD ARTICLES
====================================================== */

async function loadArticles() {

try {

const response =
await fetch(

`https://api.github.com/repos/${GITHUB_OWNER}/${GITHUB_REPO}/contents/articles?ref=${GITHUB_BRANCH}`

);


if(!response.ok)
return;


const files =
await response.json();


const list =
document
.getElementById("articles");


list.innerHTML = "";


let articleCount =
0;


for(const file of files) {

if(!file.name.endsWith(".json"))
continue;


const data =
await fetch(
file.download_url
);

const article =
await data.json();


articleCount++;


const row =
document
.createElement("div");

row.className =
"article";


row.innerHTML = `

<div class="date">
${escapeHTML(article.date)}
</div>

<div class="article-title">
${escapeHTML(article.title)}
</div>

<div>

<a
class="secondary"
href="${safeURL(article.url)}"
target="_blank"
rel="noopener noreferrer">

Read Article

</a>

</div>

`;


list.appendChild(row);

}


if(articleCount > 0) {

document
.getElementById("coming")
.style.display =
"none";

}

} catch(error) {

console.error(error);

}

}


/* ======================================================
   SECURITY HELPERS
====================================================== */

function escapeHTML(
text
) {

return String(text)
.replaceAll("&","&amp;")
.replaceAll("<","&lt;")
.replaceAll(">","&gt;")
.replaceAll('"',"&quot;")
.replaceAll("'","&#039;");

}


function safeURL(
url
) {

try {

const parsed =
new URL(url);

if(
parsed.protocol !== "http:" &&
parsed.protocol !== "https:"
) {

return "#";

}

return parsed.href;

} catch {

return "#";

}

}


/* ======================================================
   START
====================================================== */

loadPhotos();

loadArticles();

</script>

</body>
</html>