<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Your Name — Personal Portfolio</title>

    <meta name="description"
          content="Personal portfolio featuring photography, political research, and newspaper articles.">

    <style>

        /* =========================================================
           GLOBAL
        ========================================================= */

        :root {
            --background: #f4f1eb;
            --paper: #fffdf8;
            --black: #151515;
            --gray: #68645e;
            --light-gray: #d8d3ca;
            --accent: #9e3027;
            --white: #ffffff;

            --max-width: 1250px;
            --header-height: 78px;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            background: var(--background);
            color: var(--black);
            font-family: Arial, Helvetica, sans-serif;
            line-height: 1.5;
        }

        button,
        input,
        textarea {
            font-family: inherit;
        }

        button {
            cursor: pointer;
        }

        a {
            color: inherit;
        }

        .container {
            width: min(var(--max-width), calc(100% - 50px));
            margin: auto;
        }


        /* =========================================================
           HEADER / NAVIGATION
        ========================================================= */

        header {
            position: sticky;
            top: 0;
            z-index: 1000;

            height: var(--header-height);

            background: rgba(244, 241, 235, 0.95);
            backdrop-filter: blur(15px);

            border-bottom: 1px solid var(--light-gray);
        }

        .navbar {
            height: 100%;

            display: flex;
            align-items: center;
            justify-content: space-between;

            gap: 30px;
        }

        .logo {
            font-family: Georgia, "Times New Roman", serif;

            font-size: 25px;
            font-weight: bold;

            letter-spacing: -1px;

            white-space: nowrap;
        }

        .navigation {
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .navigation button {
            border: none;
            background: transparent;

            padding: 10px 14px;

            font-size: 11px;
            font-weight: bold;

            letter-spacing: 1.5px;
            text-transform: uppercase;

            transition: 0.2s;
        }

        .navigation button:hover {
            color: var(--accent);
        }

        .mobile-menu-button {
            display: none;

            background: transparent;

            border: 1px solid var(--light-gray);

            padding: 10px 13px;

            font-size: 11px;
            font-weight: bold;

            letter-spacing: 1px;
        }


        /* =========================================================
           HOME
        ========================================================= */

        .home {
            min-height: calc(100vh - var(--header-height));

            display: grid;

            grid-template-columns: 1.15fr 0.85fr;

            gap: 70px;

            align-items: center;

            padding-top: 80px;
            padding-bottom: 100px;
        }

        .eyebrow {
            color: var(--accent);

            font-size: 11px;
            font-weight: bold;

            letter-spacing: 3px;

            text-transform: uppercase;

            margin-bottom: 22px;
        }

        .home-title {
            font-family: Georgia, "Times New Roman", serif;

            font-size: clamp(60px, 9vw, 125px);

            line-height: 0.86;

            letter-spacing: -7px;

            margin-bottom: 35px;
        }

        .home-bio {
            max-width: 650px;

            color: #4e4a44;

            font-size: 19px;

            line-height: 1.7;
        }

        .home-photo {
            width: 100%;

            aspect-ratio: 4 / 5;

            background: #ded9d0;

            overflow: hidden;

            box-shadow:
                0 25px 60px rgba(0, 0, 0, 0.10);
        }

        .home-photo img {
            width: 100%;
            height: 100%;

            display: block;

            object-fit: cover;
        }

        .photo-placeholder {
            width: 100%;
            height: 100%;

            display: flex;

            align-items: center;
            justify-content: center;

            text-align: center;

            padding: 30px;

            color: #777;

            font-family: Georgia, "Times New Roman", serif;

            font-size: 22px;
        }


        /* =========================================================
           SECTIONS
        ========================================================= */

        section {
            scroll-margin-top: var(--header-height);
        }

        .section {
            border-top: 1px solid var(--light-gray);

            padding: 100px 0;
        }

        .section-header {
            display: flex;

            justify-content: space-between;
            align-items: flex-end;

            gap: 30px;

            margin-bottom: 35px;
        }

        .section-number {
            color: var(--gray);

            font-size: 11px;
            font-weight: bold;

            letter-spacing: 3px;

            margin-bottom: 10px;
        }

        .section-title {
            font-family: Georgia, "Times New Roman", serif;

            font-size: clamp(45px, 6vw, 80px);

            line-height: 0.9;

            letter-spacing: -4px;
        }

        .section-description {
            max-width: 700px;

            color: var(--gray);

            line-height: 1.7;

            margin-bottom: 40px;
        }

        .edit-button {
            border: none;

            background: transparent;

            color: var(--black);

            padding: 10px 0;

            font-size: 11px;
            font-weight: bold;

            letter-spacing: 2px;

            text-transform: uppercase;

            border-bottom: 1px solid var(--black);

            transition: 0.2s;
        }

        .edit-button:hover {
            color: var(--accent);

            border-color: var(--accent);
        }


        /* =========================================================
           PHOTOGRAPHY
        ========================================================= */

        .gallery {
            columns: 3 280px;

            column-gap: 18px;
        }

        .gallery-item {
            break-inside: avoid;

            margin-bottom: 18px;

            background: var(--paper);
        }

        .gallery-item img {
            width: 100%;

            display: block;

            height: auto;
        }

        .gallery-caption {
            padding: 12px 14px;

            font-family: Georgia, "Times New Roman", serif;

            font-size: 14px;
        }

        .empty-state {
            border: 1px dashed #bcb6ad;

            background: rgba(255,255,255,0.3);

            padding: 60px 30px;

            text-align: center;

            color: var(--gray);

            font-family: Georgia, "Times New Roman", serif;

            font-size: 20px;
        }


        /* =========================================================
           RESEARCH
        ========================================================= */

        .document-grid {
            display: grid;

            grid-template-columns: repeat(2, 1fr);

            gap: 18px;
        }

        .document {
            background: var(--paper);

            border: 1px solid var(--light-gray);

            padding: 28px;
        }

        .document-title {
            font-family: Georgia, "Times New Roman", serif;

            font-size: 24px;

            margin-bottom: 10px;
        }

        .document-description {
            color: var(--gray);

            line-height: 1.6;

            margin-bottom: 20px;
        }

        .document-link {
            display: inline-block;

            font-size: 12px;
            font-weight: bold;

            text-decoration: none;

            border-bottom: 1px solid var(--black);

            padding-bottom: 3px;
        }


        /* =========================================================
           ARTICLES
        ========================================================= */

        .article-list {
            display: grid;

            gap: 15px;
        }

        .article {
            background: var(--paper);

            border: 1px solid var(--light-gray);

            padding: 25px 28px;

            display: flex;

            justify-content: space-between;
            align-items: center;

            gap: 30px;
        }

        .article-title {
            font-family: Georgia, "Times New Roman", serif;

            font-size: 25px;

            margin-bottom: 5px;
        }

        .article-date {
            color: var(--gray);

            font-size: 13px;
        }

        .article-link {
            font-size: 12px;
            font-weight: bold;

            text-decoration: none;

            white-space: nowrap;

            border-bottom: 1px solid var(--black);

            padding-bottom: 4px;
        }

        .coming-soon {
            padding: 35px 0;

            font-family: Georgia, "Times New Roman", serif;

            font-size: 23px;

            font-style: italic;

            color: var(--gray);
        }


        /* =========================================================
           FOOTER
        ========================================================= */

        footer {
            border-top: 1px solid var(--light-gray);

            padding: 45px 0;

            color: var(--gray);

            font-size: 12px;
        }

        .footer-content {
            display: flex;

            justify-content: space-between;

            gap: 20px;
        }


        /* =========================================================
           MODAL
        ========================================================= */

        .modal-background {
            position: fixed;

            inset: 0;

            z-index: 5000;

            background: rgba(15, 15, 15, 0.65);

            display: none;

            align-items: center;
            justify-content: center;

            padding: 20px;
        }

        .modal-background.active {
            display: flex;
        }

        .modal {
            width: min(600px, 100%);

            max-height: 90vh;

            overflow-y: auto;

            background: var(--background);

            padding: 35px;

            box-shadow:
                0 30px 100px rgba(0,0,0,0.3);
        }

        .modal-title {
            font-family: Georgia, "Times New Roman", serif;

            font-size: 36px;

            margin-bottom: 25px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;

            font-size: 11px;
            font-weight: bold;

            letter-spacing: 1.5px;

            text-transform: uppercase;

            margin-bottom: 8px;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;

            border: 1px solid var(--light-gray);

            background: var(--white);

            padding: 13px;

            font-size: 15px;

            outline: none;
        }

        .form-group textarea {
            min-height: 130px;

            resize: vertical;
        }

        .modal-actions {
            display: flex;

            justify-content: flex-end;

            gap: 10px;

            margin-top: 25px;
        }

        .primary-button,
        .secondary-button {
            padding: 12px 18px;

            border: 1px solid var(--black);

            font-size: 12px;
            font-weight: bold;

            cursor: pointer;
        }

        .primary-button {
            background: var(--black);

            color: var(--white);
        }

        .secondary-button {
            background: transparent;

            color: var(--black);
        }

        .warning {
            color: var(--accent);

            font-size: 12px;

            line-height: 1.5;

            margin-top: 10px;
        }


        /* =========================================================
           PASSWORD SCREEN
        ========================================================= */

        .password-box {
            text-align: center;
        }

        .password-box input {
            width: 180px;

            text-align: center;

            font-size: 28px;

            letter-spacing: 8px;

            padding: 13px;

            border: 1px solid var(--light-gray);

            background: white;

            margin: 15px 0;
        }

        .password-error {
            color: var(--accent);

            font-size: 13px;

            display: none;

            margin-top: 10px;
        }


        /* =========================================================
           DELETE BUTTONS
        ========================================================= */

        .delete-button {
            border: none;

            background: transparent;

            color: var(--accent);

            font-size: 10px;

            font-weight: bold;

            letter-spacing: 1px;

            text-transform: uppercase;

            margin-top: 10px;
        }


        /* =========================================================
           RESPONSIVE — TABLET
        ========================================================= */

        @media (max-width: 850px) {

            .container {
                width: min(100% - 35px, var(--max-width));
            }

            .home {
                grid-template-columns: 1fr;

                gap: 45px;

                padding-top: 60px;
            }

            .home-photo {
                max-width: 650px;
            }

            .document-grid {
                grid-template-columns: 1fr;
            }

            .navigation {
                display: none;

                position: absolute;

                top: var(--header-height);

                left: 0;
                right: 0;

                background: var(--background);

                border-bottom: 1px solid var(--light-gray);

                padding: 10px 20px;

                flex-direction: column;

                align-items: stretch;
            }

            .navigation.open {
                display: flex;
            }

            .navigation button {
                text-align: left;

                padding: 14px;
            }

            .mobile-menu-button {
                display: block;
            }
        }


        /* =========================================================
           RESPONSIVE — PHONE
        ========================================================= */

        @media (max-width: 600px) {

            :root {
                --header-height: 65px;
            }

            .container {
                width: calc(100% - 28px);
            }

            .home {
                padding-top: 45px;

                padding-bottom: 70px;
            }

            .home-title {
                font-size: 62px;

                letter-spacing: -4px;
            }

            .home-bio {
                font-size: 17px;
            }

            .section {
                padding: 70px 0;
            }

            .section-header {
                align-items: flex-start;

                flex-direction: column;

                gap: 20px;
            }

            .section-title {
                font-size: 48px;

                letter-spacing: -3px;
            }

            .gallery {
                columns: 1;
            }

            .article {
                flex-direction: column;

                align-items: flex-start;
            }

            .article-link {
                white-space: normal;
            }

            .footer-content {
                flex-direction: column;
            }

            .modal {
                padding: 25px;
            }
        }

    </style>
</head>


<body>


<!-- ============================================================
     NAVIGATION
============================================================ -->

<header>

    <div class="container navbar">

        <div class="logo" id="navigationName">
            YOUR NAME
        </div>

        <button
            class="mobile-menu-button"
            onclick="toggleMobileMenu()"
        >
            MENU
        </button>

        <nav class="navigation" id="navigation">

            <button onclick="goToSection('home')">
                Home
            </button>

            <button onclick="goToSection('photography')">
                Photography
            </button>

            <button onclick="goToSection('research')">
                Political Research
            </button>

            <button onclick="goToSection('articles')">
                Newspaper
            </button>

        </nav>

    </div>

</header>



<!-- ============================================================
     HOMEPAGE
============================================================ -->

<main>

<section id="home">

    <div class="container home">

        <div>

            <div class="eyebrow">
                Portfolio / Journal / Work
            </div>

            <h1
                class="home-title"
                id="homeName"
            >
                YOUR<br>
                NAME
            </h1>

            <p
                class="home-bio"
                id="homeBio"
            >
                Write your biography here. Talk about who you are,
                what you care about, and the work you are creating.
            </p>

            <br>

            <button
                class="edit-button"
                onclick="startEditing('home')"
            >
                Edit
            </button>

        </div>


        <div
            class="home-photo"
            id="homePhoto"
        >

            <div class="photo-placeholder">

                Your portrait<br>
                will appear here.

            </div>

        </div>

    </div>

</section>



<!-- ============================================================
     PHOTOGRAPHY
============================================================ -->

<section
    class="section"
    id="photography"
>

    <div class="container">

        <div class="section-header">

            <div>

                <div class="section-number">
                    01 / VISUAL WORK
                </div>

                <h2 class="section-title">
                    Photography
                </h2>

            </div>

            <button
                class="edit-button"
                onclick="startEditing('photography')"
            >
                Edit
            </button>

        </div>


        <p class="section-description">

            A visual archive of photographs, places, people,
            ideas and moments.

        </p>


        <div
            class="gallery"
            id="gallery"
        >

            <div class="empty-state">

                Your photography gallery is ready.

                <br><br>

                Click <strong>Edit</strong> to add photographs
                from your camera roll.

            </div>

        </div>

    </div>

</section>



<!-- ============================================================
     POLITICAL RESEARCH
============================================================ -->

<section
    class="section"
    id="research"
>

    <div class="container">

        <div class="section-header">

            <div>

                <div class="section-number">
                    02 / NOTES & SOURCES
                </div>

                <h2 class="section-title">
                    Political<br>
                    Research
                </h2>

            </div>

            <button
                class="edit-button"
                onclick="startEditing('research')"
            >
                Edit
            </button>

        </div>


        <p class="section-description">

            Research documents, notes, sources and projects.
            Use this section as your personal research archive.

        </p>


        <div
            class="document-grid"
            id="documentGrid"
        >

            <div class="empty-state">

                No research documents yet.

                <br><br>

                Click <strong>Edit</strong> to add one.

            </div>

        </div>

    </div>

</section>



<!-- ============================================================
     SCHOOL NEWSPAPER
============================================================ -->

<section
    class="section"
    id="articles"
>

    <div class="container">

        <div class="section-header">

            <div>

                <div class="section-number">
                    03 / SCHOOL NEWSPAPER
                </div>

                <h2 class="section-title">
                    Articles
                </h2>

            </div>

            <button
                class="edit-button"
                onclick="startEditing('articles')"
            >
                Edit
            </button>

        </div>


        <p class="section-description">

            Published writing and reporting from the school newspaper.

        </p>


        <div
            class="article-list"
            id="articleList"
        >

            <!-- Coming soon is automatically replaced
                 once an article is added. -->

        </div>

    </div>

</section>

</main>



<!-- ============================================================
     FOOTER
============================================================ -->

<footer>

    <div class="container footer-content">

        <span id="footerName">
            YOUR NAME
        </span>

        <span>
            © <span id="currentYear"></span>
            — Personal Portfolio
        </span>

    </div>

</footer>



<!-- ============================================================
     EDIT MODAL
============================================================ -->

<div
    class="modal-background"
    id="modalBackground"
>

    <div
        class="modal"
        id="modal"
    >

    </div>

</div>



<script>

/*
==================================================================
                         WEBSITE SETTINGS
==================================================================

EDIT CODE:

4547

IMPORTANT:

This is a front-end HTML website.

The code protects the editing interface, but it is NOT real
server-side security.

Someone who knows how to inspect the HTML/JavaScript can find
the code.

For a truly private political research archive, a future version
should use an actual login/account system and server-side security.

==================================================================
*/


/* ================================================================
   WEBSITE DATA
================================================================ */

const EDIT_CODE = "4547";

const STORAGE_KEY = "myMagazinePortfolio_v2";


const defaultData = {

    name: "YOUR NAME",

    bio:
        "Write your biography here. Talk about who you are, " +
        "what you care about, and the work you are creating.",

    profilePhoto: "",

    photos: [],

    documents: [],

    articles: []

};



let websiteData = loadWebsiteData();



/* ================================================================
   LOAD DATA
================================================================ */

function loadWebsiteData() {

    try {

        const saved =
            localStorage.getItem(STORAGE_KEY);

        if (!saved) {

            return {
                ...defaultData
            };

        }

        const parsed =
            JSON.parse(saved);

        return {
            ...defaultData,
            ...parsed
        };

    } catch (error) {

        console.error(
            "Could not load website data:",
            error
        );

        return {
            ...defaultData
        };

    }

}



/* ================================================================
   SAVE DATA
================================================================ */

function saveWebsiteData() {

    try {

        localStorage.setItem(
            STORAGE_KEY,
            JSON.stringify(websiteData)
        );

    } catch (error) {

        alert(
            "Your browser could not save this change. " +
            "Large photo or document files may have exceeded " +
            "the browser's storage limit."
        );

        console.error(error);

    }

}



/* ================================================================
   NAVIGATION
================================================================ */

function goToSection(sectionID) {

    const section =
        document.getElementById(sectionID);

    if (!section) {
        return;
    }

    section.scrollIntoView({
        behavior: "smooth"
    });

    document
        .getElementById("navigation")
        .classList.remove("open");

}



function toggleMobileMenu() {

    document
        .getElementById("navigation")
        .classList.toggle("open");

}



/* ================================================================
   ESCAPE HTML
================================================================ */

function escapeHTML(value) {

    return String(value ?? "")
        .replace(/&/g, "&amp;")
        .replace(/</g, "&lt;")
        .replace(/>/g, "&gt;")
        .replace(/"/g, "&quot;")
        .replace(/'/g, "&#039;");

}



/* ================================================================
   MODAL
================================================================ */

function openModal(content) {

    document.getElementById(
        "modal"
    ).innerHTML = content;

    document
        .getElementById("modalBackground")
        .classList.add("active");

}



function closeModal() {

    document
        .getElementById("modalBackground")
        .classList.remove("active");

}



/* Close modal when clicking outside */

document
    .getElementById("modalBackground")
    .addEventListener(
        "click",
        function(event) {

            if (
                event.target.id ===
                "modalBackground"
            ) {

                closeModal();

            }

        }
    );



/* ================================================================
   EDIT AUTHENTICATION
================================================================ */

function startEditing(page) {

    const code =
        prompt(
            "Enter your 4-digit edit code:"
        );

    if (code === null) {
        return;
    }

    if (code !== EDIT_CODE) {

        alert(
            "Incorrect edit code."
        );

        return;

    }


    if (page === "home") {

        showHomeEditor();

    }


    if (page === "photography") {

        showPhotographyEditor();

    }


    if (page === "research") {

        showResearchEditor();

    }


    if (page === "articles") {

        showArticleEditor();

    }

}



/* ================================================================
   HOMEPAGE EDITOR
================================================================ */

function showHomeEditor() {

    openModal(`

        <h3 class="modal-title">
            Edit Homepage
        </h3>


        <div class="form-group">

            <label>
                Your Name
            </label>

            <input
                id="editName"
                type="text"
                value="${escapeHTML(websiteData.name)}"
                placeholder="Your Name"
            >

        </div>


        <div class="form-group">

            <label>
                Biography
            </label>

            <textarea
                id="editBio"
                placeholder="Write your bio..."
            >${escapeHTML(websiteData.bio)}</textarea>

        </div>


        <div class="form-group">

            <label>
                Profile Photo
            </label>

            <input
                id="editProfilePhoto"
                type="file"
                accept="image/*"
            >

        </div>


        <p class="warning">

            Your photo is stored in this browser.

        </p>


        <div class="modal-actions">

            <button
                class="secondary-button"
                onclick="closeModal()"
            >
                Cancel
            </button>

            <button
                class="primary-button"
                onclick="saveHomepage()"
            >
                Save Changes
            </button>

        </div>

    `);

}



/* ================================================================
   SAVE HOMEPAGE
================================================================ */

async function saveHomepage() {

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

    const photoInput =
        document.getElementById(
            "editProfilePhoto"
        );


    websiteData.name =
        name || "YOUR NAME";

    websiteData.bio =
        bio ||
        defaultData.bio;


    if (
        photoInput.files &&
        photoInput.files.length > 0
    ) {

        websiteData.profilePhoto =
            await fileToDataURL(
                photoInput.files[0]
            );

    }


    saveWebsiteData();

    renderWebsite();

    closeModal();

}



/* ================================================================
   PHOTOGRAPHY EDITOR
================================================================ */

function showPhotographyEditor() {

    openModal(`

        <h3 class="modal-title">
            Add Photography
        </h3>


        <div class="form-group">

            <label>
                Choose Photos
            </label>

            <input
                id="photoFiles"
                type="file"
                accept="image/*"
                multiple
            >

        </div>


        <p class="warning">

            You can select multiple photographs
            from your computer or camera roll.

        </p>


        <div class="modal-actions">

            <button
                class="secondary-button"
                onclick="closeModal()"
            >
                Cancel
            </button>

            <button
                class="primary-button"
                onclick="addPhotography()"
            >
                Add Photos
            </button>

        </div>

    `);

}



/* ================================================================
   ADD PHOTOS
================================================================ */

async function addPhotography() {

    const input =
        document.getElementById(
            "photoFiles"
        );

    const files =
        Array.from(input.files || []);


    if (files.length === 0) {

        alert(
            "Please choose at least one photo."
        );

        return;

    }


    for (const file of files) {

        try {

            const dataURL =
                await fileToDataURL(file);

            websiteData.photos.push({

                image: dataURL,

                name: file.name

            });

        } catch (error) {

            console.error(
                "Could not load photo:",
                error
            );

        }

    }


    saveWebsiteData();

    renderWebsite();

    closeModal();

}



/* ================================================================
   DELETE PHOTO
================================================================ */

function deletePhoto(index) {

    const confirmed =
        confirm(
            "Remove this photograph?"
        );

    if (!confirmed) {
        return;
    }


    websiteData.photos.splice(
        index,
        1
    );

    saveWebsiteData();

    renderWebsite();

}



/* ================================================================
   RESEARCH EDITOR
================================================================ */

function showResearchEditor() {

    openModal(`

        <h3 class="modal-title">
            Add Research
        </h3>


        <div class="form-group">

            <label>
                Document Title
            </label>

            <input
                id="documentTitle"
                type="text"
                placeholder="Example: 2026 Election Research"
            >

        </div>


        <div class="form-group">

            <label>
                Description
            </label>

            <textarea
                id="documentDescription"
                placeholder="Describe this research..."
            ></textarea>

        </div>


        <div class="form-group">

            <label>
                Document
            </label>

            <input
                id="documentFile"
                type="file"
                accept=".pdf,.doc,.docx,.txt"
            >

        </div>


        <p class="warning">

            Research documents are stored in this browser.
            Very large files may exceed browser storage limits.

        </p>


        <div class="modal-actions">

            <button
                class="secondary-button"
                onclick="closeModal()"
            >
                Cancel
            </button>

            <button
                class="primary-button"
                onclick="addResearchDocument()"
            >
                Add Document
            </button>

        </div>

    `);

}



/* ================================================================
   ADD RESEARCH DOCUMENT
================================================================ */

async function addResearchDocument() {

    const title =
        document
            .getElementById(
                "documentTitle"
            )
            .value
            .trim();


    const description =
        document
            .getElementById(
                "documentDescription"
            )
            .value
            .trim();


    const fileInput =
        document.getElementById(
            "documentFile"
        );


    if (
        !title ||
        !fileInput.files ||
        fileInput.files.length === 0
    ) {

        alert(
            "Please add a title and choose a document."
        );

        return;

    }


    const file =
        fileInput.files[0];


    try {

        const dataURL =
            await fileToDataURL(file);


        websiteData.documents.push({

            title: title,

            description: description,

            file: dataURL,

            fileName: file.name

        });


        saveWebsiteData();

        renderWebsite();

        closeModal();

    } catch (error) {

        alert(
            "The document could not be added."
        );

        console.error(error);

    }

}



/* ================================================================
   DELETE RESEARCH DOCUMENT
================================================================ */

function deleteDocument(index) {

    const confirmed =
        confirm(
            "Remove this research document?"
        );

    if (!confirmed) {
        return;
    }


    websiteData.documents.splice(
        index,
        1
    );

    saveWebsiteData();

    renderWebsite();

}



/* ================================================================
   ARTICLE EDITOR
================================================================ */

function showArticleEditor() {

    openModal(`

        <h3 class="modal-title">
            Add Newspaper Article
        </h3>


        <div class="form-group">

            <label>
                Article Title
            </label>

            <input
                id="articleTitle"
                type="text"
                placeholder="My First Article"
            >

        </div>


        <div class="form-group">

            <label>
                Publication Date
            </label>

            <input
                id="articleDate"
                type="date"
            >

        </div>


        <div class="form-group">

            <label>
                Article Link
            </label>

            <input
                id="articleURL"
                type="url"
                placeholder="https://..."
            >

        </div>


        <p class="warning">

            Once you add your first article,
            the “Coming September 16” message
            will disappear permanently.

        </p>


        <div class="modal-actions">

            <button
                class="secondary-button"
                onclick="closeModal()"
            >
                Cancel
            </button>

            <button
                class="primary-button"
                onclick="addArticle()"
            >
                Add Article
            </button>

        </div>

    `);

}



/* ================================================================
   ADD ARTICLE
================================================================ */

function addArticle() {

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
            .value;


    let url =
        document
            .getElementById(
                "articleURL"
            )
            .value
            .trim();


    if (!title || !url) {

        alert(
            "Please enter an article title and link."
        );

        return;

    }


    if (
        !/^https?:\/\//i.test(url)
    ) {

        url =
            "https://" + url;

    }


    websiteData.articles.push({

        title: title,

        date: date,

        url: url

    });


    saveWebsiteData();

    renderWebsite();

    closeModal();

}



/* ================================================================
   DELETE ARTICLE
================================================================ */

function deleteArticle(index) {

    const confirmed =
        confirm(
            "Remove this article?"
        );

    if (!confirmed) {
        return;
    }


    websiteData.articles.splice(
        index,
        1
    );


    saveWebsiteData();

    renderWebsite();

}



/* ================================================================
   FILE READER
================================================================ */

function fileToDataURL(file) {

    return new Promise(
        (resolve, reject) => {

            const reader =
                new FileReader();


            reader.onload =
                () => resolve(
                    reader.result
                );


            reader.onerror =
                () => reject(
                    reader.error
                );


            reader.readAsDataURL(
                file
            );

        }
    );

}



/* ================================================================
   FORMAT DATE
================================================================ */

function formatDate(dateString) {

    if (!dateString) {
        return "";
    }


    const date =
        new Date(
            dateString + "T12:00:00"
        );


    if (
        Number.isNaN(
            date.getTime()
        )
    ) {

        return "";

    }


    return date.toLocaleDateString(
        undefined,
        {
            month: "long",
            day: "numeric",
            year: "numeric"
        }
    );

}



/* ================================================================
   RENDER HOMEPAGE
================================================================ */

function renderHomepage() {

    const name =
        websiteData.name ||
        "YOUR NAME";


    const bio =
        websiteData.bio ||
        defaultData.bio;


    document
        .getElementById(
            "navigationName"
        )
        .textContent =
        name;


    document
        .getElementById(
            "footerName"
        )
        .textContent =
        name;


    document
        .getElementById(
            "homeBio"
        )
        .textContent =
        bio;


    const nameParts =
        name
            .trim()
            .split(/\s+/);


    let formattedName = "";


    if (
        nameParts.length === 1
    ) {

        formattedName =
            escapeHTML(
                nameParts[0]
            );

    } else {

        formattedName =
            escapeHTML(
                nameParts[0]
            ) +
            "<br>" +
            escapeHTML(
                nameParts
                    .slice(1)
                    .join(" ")
            );

    }


    document
        .getElementById(
            "homeName"
        )
        .innerHTML =
        formattedName;


    const photoContainer =
        document.getElementById(
            "homePhoto"
        );


    if (
        websiteData.profilePhoto
    ) {

        photoContainer.innerHTML = `

            <img
                src="${websiteData.profilePhoto}"
                alt="${escapeHTML(name)}"
            >

        `;

    } else {

        photoContainer.innerHTML = `

            <div class="photo-placeholder">

                Your portrait<br>
                will appear here.

            </div>

        `;

    }

}



/* ================================================================
   RENDER PHOTOGRAPHY
================================================================ */

function renderPhotography() {

    const gallery =
        document.getElementById(
            "gallery"
        );


    if (
        websiteData.photos.length === 0
    ) {

        gallery.innerHTML = `

            <div class="empty-state">

                Your photography gallery is ready.

                <br><br>

                Click <strong>Edit</strong>
                to add photographs
                from your camera roll.

            </div>

        `;

        return;

    }


    gallery.innerHTML =
        websiteData.photos
            .map(
                (photo, index) => `

                    <figure
                        class="gallery-item"
                    >

                        <img
                            src="${photo.image}"
                            alt="${escapeHTML(
                                photo.name ||
                                "Photography"
                            )}"
                        >

                        <figcaption
                            class="gallery-caption"
                        >

                            ${escapeHTML(
                                photo.name ||
                                "Untitled photograph"
                            )}

                            <br>

                            <button
                                class="delete-button"
                                onclick="deletePhoto(${index})"
                            >
                                Delete
                            </button>

                        </figcaption>

                    </figure>

                `
            )
            .join("");

}



/* ================================================================
   RENDER RESEARCH
================================================================ */

function renderResearch() {

    const grid =
        document.getElementById(
            "documentGrid"
        );


    if (
        websiteData.documents.length === 0
    ) {

        grid.innerHTML = `

            <div class="empty-state">

                No research documents yet.

                <br><br>

                Click <strong>Edit</strong>
                to add one.

            </div>

        `;

        return;

    }


    grid.innerHTML =
        websiteData.documents
            .map(
                (documentItem, index) => `

                    <article
                        class="document"
                    >

                        <h3
                            class="document-title"
                        >
                            ${escapeHTML(
                                documentItem.title
                            )}
                        </h3>


                        <p
                            class="document-description"
                        >
                            ${escapeHTML(
                                documentItem.description
                            )}
                        </p>


                        <a
                            class="document-link"
                            href="${documentItem.file}"
                            download="${escapeHTML(
                                documentItem.fileName
                            )}"
                        >
                            Open Document →
                        </a>


                        <br>


                        <button
                            class="delete-button"
                            onclick="deleteDocument(${index})"
                        >
                            Delete
                        </button>

                    </article>

                `
            )
            .join("");

}



/* ================================================================
   RENDER ARTICLES
================================================================ */

function renderArticles() {

    const list =
        document.getElementById(
            "articleList"
        );


    /*
       IMPORTANT:

       We do NOT store a separate "coming soon" variable.

       Therefore:

       0 articles =
       Coming September 16

       1 or more articles =
       Coming September 16 disappears.

       It cannot return unless every article is manually deleted,
       which is why we keep a permanent "has published" flag below.
    */


    if (
        websiteData.articles.length === 0
    ) {

        if (
            localStorage.getItem(
                "newspaperHasPublishedArticle"
            ) === "true"
        ) {

            list.innerHTML = `

                <div class="empty-state">

                    Your published articles will appear here.

                </div>

            `;

        } else {

            list.innerHTML = `

                <div class="coming-soon">

                    Coming September 16 —
                    school newspaper articles
                    will appear here.

                </div>

            `;

        }

        return;

    }


    /*
       Once there is an article,
       permanently remember that publication has started.
    */

    localStorage.setItem(
        "newspaperHasPublishedArticle",
        "true"
    );


    list.innerHTML =
        websiteData.articles
            .map(
                (article, index) => `

                    <article
                        class="article"
                    >

                        <div>

                            <h3
                                class="article-title"
                            >
                                ${escapeHTML(
                                    article.title
                                )}
                            </h3>


                            <div
                                class="article-date"
                            >
                                ${formatDate(
                                    article.date
                                )}
                            </div>

                        </div>


                        <div>

                            <a
                                class="article-link"
                                href="${escapeHTML(
                                    article.url
                                )}"
                                target="_blank"
                                rel="noopener noreferrer"
                            >
                                Read Article →
                            </a>


                            <br>


                            <button
                                class="delete-button"
                                onclick="deleteArticle(${index})"
                            >
                                Delete
                            </button>

                        </div>

                    </article>

                `
            )
            .join("");

}



/* ================================================================
   RENDER EVERYTHING
================================================================ */

function renderWebsite() {

    renderHomepage();

    renderPhotography();

    renderResearch();

    renderArticles();


    document
        .getElementById(
            "currentYear"
        )
        .textContent =
        new Date().getFullYear();

}



/* ================================================================
   START WEBSITE
================================================================ */

renderWebsite();


</script>


</body>
</html># graysengottman
My website
