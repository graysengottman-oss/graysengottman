<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta
    name="viewport"
    content="width=device-width, initial-scale=1.0"
>
<meta
    name="theme-color"
    content="#F3EBDD"
>
<title>Graysen</title>
<style>
/* =========================================================
   GRAYSEN PORTFOLIO
   ONE-FILE WEBSITE
   LOCAL STORAGE ONLY
========================================================= */
/* =========================================================
   COLOR SYSTEM
========================================================= */
:root {
    --tan: #F3EBDD;
    --tan-2: #EDE2CF;
    --cream: #FAF7F0;
    --cream-2: #FFFDF8;
    --black: #111111;
    --black-soft: #252525;
    --gray: #656565;
    --gray-light: #898989;
    --green: #2F6B4F;
    --green-dark: #24533D;
    --green-light: #DCE8DF;
    --green-pale: #EEF4EF;
    --border: #D7CBB9;
    --border-dark: #C6B8A4;
    --danger: #8D3434;
    --shadow:
        0 15px 45px rgba(0,0,0,0.10);
    --shadow-large:
        0 25px 80px rgba(0,0,0,0.18);
    --radius: 16px;
}
/* =========================================================
   RESET
========================================================= */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
html {
    scroll-behavior: smooth;
}
body {
    min-height: 100vh;
    background: var(--tan);
    color: var(--black);
    font-family:
        Inter,
        -apple-system,
        BlinkMacSystemFont,
        "Segoe UI",
        Arial,
        sans-serif;
    line-height: 1.6;
}
button,
input,
textarea {
    font: inherit;
}
button {
    -webkit-tap-highlight-color:
        transparent;
}
img {
    max-width: 100%;
}
/* =========================================================
   GLOBAL
========================================================= */
.container {
    width: min(
        1180px,
        calc(100% - 40px)
    );
    margin: 0 auto;
}
.hidden {
    display: none !important;
}
/* =========================================================
   HEADER
========================================================= */
.site-header {
    position: sticky;
    top: 0;
    z-index: 1000;
    background:
        rgba(243,235,221,0.92);
    backdrop-filter:
        blur(18px);
    -webkit-backdrop-filter:
        blur(18px);
    border-bottom:
        1px solid var(--border);
}
.header-inner {
    min-height: 74px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 25px;
}
/* NAME */
.logo {
    color: var(--black);
    text-decoration: none;
    font-size: 25px;
    font-weight: 850;
    letter-spacing: -1.4px;
    white-space: nowrap;
}
.logo::after {
    content: ".";
    color: var(--green);
}
/* NAVIGATION */
.desktop-nav {
    display: flex;
    align-items: center;
    gap: 5px;
}
.nav-button {
    border: 0;
    background: transparent;
    color: var(--black);
    padding: 9px 13px;
    border-radius: 9px;
    font-size: 14px;
    font-weight: 700;
    cursor: pointer;
    transition:
        background .2s ease,
        color .2s ease,
        transform .2s ease;
}
.nav-button:hover {
    background: var(--green-light);
    color: var(--green-dark);
}
.nav-button.active {
    background: var(--green);
    color: white;
}
/* MOBILE MENU BUTTON */
.menu-button {
    display: none;
    width: 42px;
    height: 42px;
    border: 1px solid var(--border);
    background: var(--cream);
    color: var(--black);
    border-radius: 10px;
    cursor: pointer;
    font-size: 20px;
}
/* =========================================================
   MOBILE NAV
========================================================= */
.mobile-nav {
    display: none;
    padding: 0 20px 15px;
}
.mobile-nav.open {
    display: grid;
    gap: 5px;
}
.mobile-nav button {
    text-align: left;
    border: 0;
    background: transparent;
    padding: 12px 14px;
    border-radius: 9px;
    font-weight: 700;
    color: var(--black);
}
.mobile-nav button.active {
    background: var(--green);
    color: white;
}
/* =========================================================
   MAIN
========================================================= */
main {
    min-height: calc(
        100vh - 150px
    );
}
.page {
    display: none;
    animation:
        pageIn .35s ease;
}
.page.active {
    display: block;
}
@keyframes pageIn {
    from {
        opacity: 0;
        transform:
            translateY(8px);
    }
    to {
        opacity: 1;
        transform:
            translateY(0);
    }
}
/* =========================================================
   HOME
========================================================= */
.home {
    padding:
        80px 0 100px;
}
.hero {
    min-height:
        620px;
    display: grid;
    grid-template-columns:
        1.15fr .85fr;
    align-items: center;
    gap: 80px;
}
.hero-copy {
    max-width: 720px;
}
.eyebrow {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    color: var(--green-dark);
    font-size: 13px;
    font-weight: 800;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    margin-bottom: 20px;
}
.eyebrow::before {
    content: "";
    width: 28px;
    height: 3px;
    border-radius: 10px;
    background: var(--green);
}
.hero-title {
    font-size:
        clamp(65px, 10vw, 125px);
    line-height:
        .84;
    letter-spacing:
        -8px;
    font-weight:
        850;
    margin-bottom:
        32px;
}
.hero-title .accent {
    color: var(--green);
}
.hero-description {
    max-width: 650px;
    font-size:
        clamp(17px, 2vw, 20px);
    color:
        #494949;
    margin-bottom:
        32px;
}
.hero-actions {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
}
/* HERO IMAGE */
.hero-photo-wrap {
    position: relative;
    display: flex;
    justify-content: center;
}
.hero-photo-frame {
    position: relative;
    width: min(
        390px,
        100%
    );
    aspect-ratio: 1 / 1;
}
.hero-photo {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 26px;
    background: var(--tan-2);
    border:
        8px solid var(--cream);
    box-shadow:
        var(--shadow-large);
}
.hero-photo-placeholder {
    width: 100%;
    height: 100%;
    border-radius: 26px;
    border:
        2px dashed var(--border-dark);
    background:
        var(--tan-2);
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 35px;
    color: var(--gray);
}
.hero-photo-placeholder strong {
    display: block;
    color: var(--black);
    margin-bottom: 5px;
}
/* DECORATIVE GREEN BLOCK */
.hero-photo-frame::before {
    content: "";
    position: absolute;
    width: 95px;
    height: 95px;
    right: -20px;
    bottom: -20px;
    background: var(--green);
    border-radius: 20px;
    z-index: -1;
}
/* =========================================================
   QUICK CARDS
========================================================= */
.quick-section {
    padding-bottom:
        100px;
}
.quick-grid {
    display: grid;
    grid-template-columns:
        repeat(3, 1fr);
    gap: 18px;
}
.quick-card {
    padding: 27px;
    border:
        1px solid var(--border);
    background:
        rgba(250,247,240,.78);
    border-radius:
        var(--radius);
    cursor: pointer;
    transition:
        transform .2s ease,
        box-shadow .2s ease,
        border-color .2s ease;
}
.quick-card:hover {
    transform:
        translateY(-4px);
    border-color:
        var(--green);
    box-shadow:
        var(--shadow);
}
.quick-number {
    color: var(--green);
    font-size: 12px;
    font-weight: 900;
    letter-spacing: 1px;
    margin-bottom: 14px;
}
.quick-card h3 {
    font-size: 21px;
    margin-bottom: 7px;
}
.quick-card p {
    color: var(--gray);
    font-size: 14px;
}
/* =========================================================
   SECTION HEADER
========================================================= */
.section {
    padding:
        65px 0 100px;
}
.section-heading {
    margin-bottom:
        38px;
}
.section-heading .eyebrow {
    margin-bottom:
        13px;
}
.section-title {
    font-size:
        clamp(45px, 7vw, 72px);
    line-height:
        .95;
    letter-spacing:
        -4px;
    margin-bottom:
        13px;
}
.section-subtitle {
    color: var(--gray);
    max-width: 650px;
}
.green-line {
    width: 48px;
    height: 4px;
    border-radius: 10px;
    background: var(--green);
    margin-top: 18px;
}
/* =========================================================
   PHOTO GALLERY
========================================================= */
.photo-toolbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
    gap: 15px;
}
.photo-count {
    color: var(--gray);
    font-size: 14px;
    font-weight: 700;
}
.photo-grid {
    display: grid;
    grid-template-columns:
        repeat(3, 1fr);
    gap: 18px;
}
.photo-card {
    position: relative;
    aspect-ratio: 1 / 1;
    overflow: hidden;
    background:
        var(--tan-2);
    border:
        1px solid var(--border);
    border-radius:
        15px;
    cursor: pointer;
}
.photo-card img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
    transition:
        transform .45s ease;
}
.photo-card:hover img {
    transform:
        scale(1.045);
}
.photo-overlay {
    position: absolute;
    inset: auto 0 0;
    padding: 35px 16px 15px;
    background:
        linear-gradient(
            transparent,
            rgba(0,0,0,.55)
        );
    color: white;
    opacity: 0;
    transition:
        opacity .25s ease;
}
.photo-card:hover .photo-overlay {
    opacity: 1;
}
/* =========================================================
   EMPTY STATE
========================================================= */
.empty-state {
    grid-column:
        1 / -1;
    padding:
        75px 25px;
    text-align:
        center;
    border:
        1px dashed var(--border-dark);
    border-radius:
        var(--radius);
    background:
        rgba(250,247,240,.55);
}
.empty-icon {
    width: 54px;
    height: 54px;
    margin:
        0 auto 16px;
    border-radius: 50%;
    background:
        var(--green-light);
    color:
        var(--green-dark);
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 900;
}
.empty-state h3 {
    margin-bottom: 6px;
}
.empty-state p {
    color: var(--gray);
}
/* =========================================================
   DOCUMENTS
========================================================= */
.document-grid {
    display: grid;
    grid-template-columns:
        repeat(2, 1fr);
    gap: 18px;
}
.document-card {
    background:
        var(--cream);
    border:
        1px solid var(--border);
    border-radius:
        var(--radius);
    padding:
        25px;
    transition:
        transform .2s ease,
        border-color .2s ease,
        box-shadow .2s ease;
}
.document-card:hover {
    transform:
        translateY(-3px);
    border-color:
        var(--green);
    box-shadow:
        var(--shadow);
}
.document-top {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 15px;
}
.document-icon {
    width: 43px;
    height: 43px;
    flex-shrink: 0;
    border-radius: 11px;
    background:
        var(--green-light);
    color:
        var(--green-dark);
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 900;
}
.document-card h3 {
    font-size: 20px;
    margin-bottom: 7px;
}
.document-card p {
    color:
        var(--gray);
    font-size:
        14px;
    margin:
        10px 0 20px;
}
/* =========================================================
   NEWSPAPER
========================================================= */
.article-list {
    display: grid;
    gap: 18px;
}
.article {
    display: grid;
    grid-template-columns:
        1fr auto;
    align-items: center;
    gap: 25px;
    background:
        var(--cream);
    border:
        1px solid var(--border);
    border-left:
        5px solid var(--green);
    border-radius:
        13px;
    padding:
        24px;
    transition:
        transform .2s ease,
        box-shadow .2s ease;
}
.article:hover {
    transform:
        translateX(3px);
    box-shadow:
        var(--shadow);
}
.article-label {
    color:
        var(--green-dark);
    font-size:
        11px;
    font-weight:
        900;
    letter-spacing:
        1.3px;
    text-transform:
        uppercase;
    margin-bottom:
        5px;
}
.article h3 {
    font-size:
        21px;
    margin-bottom:
        7px;
}
.article p {
    color:
        var(--gray);
    font-size:
        14px;
}
.article-link {
    white-space:
        nowrap;
}
/* =========================================================
   BUTTONS
========================================================= */
.button {
    display:
        inline-flex;
    align-items:
        center;
    justify-content:
        center;
    gap:
        8px;
    border:
        1px solid transparent;
    border-radius:
        10px;
    padding:
        11px 16px;
    background:
        var(--green);
    color:
        white;
    font-weight:
        800;
    font-size:
        14px;
    cursor:
        pointer;
    text-decoration:
        none;
    transition:
        transform .2s ease,
        background .2s ease,
        border-color .2s ease;
}
.button:hover {
    background:
        var(--green-dark);
    transform:
        translateY(-1px);
}
.button.secondary {
    background:
        var(--green-light);
    color:
        var(--green-dark);
}
.button.secondary:hover {
    background:
        #CFE0D3;
}
.button.outline {
    background:
        transparent;
    color:
        var(--black);
    border-color:
        var(--border-dark);
}
.button.outline:hover {
    border-color:
        var(--green);
    color:
        var(--green-dark);
}
.button.small {
    padding:
        9px 12px;
    font-size:
        13px;
}
/* =========================================================
   EDIT BUTTON
========================================================= */
.edit-button {
    position:
        fixed;
    z-index:
        2500;
    right:
        23px;
    bottom:
        23px;
    display:
        flex;
    align-items:
        center;
    gap:
        8px;
    border:
        0;
    border-radius:
        999px;
    padding:
        14px 19px;
    background:
        var(--green);
    color:
        white;
    font-size:
        13px;
    font-weight:
        900;
    letter-spacing:
        .7px;
    cursor:
        pointer;
    box-shadow:
        0 10px 30px
        rgba(0,0,0,.20);
    transition:
        transform .2s ease,
        background .2s ease;
}
.edit-button:hover {
    background:
        var(--green-dark);
    transform:
        translateY(-3px);
}
/* =========================================================
   MODAL
========================================================= */
.modal {
    position:
        fixed;
    inset:
        0;
    z-index:
        3000;
    display:
        none;
    align-items:
        center;
    justify-content:
        center;
    padding:
        18px;
    background:
        rgba(17,17,17,.58);
    backdrop-filter:
        blur(7px);
    -webkit-backdrop-filter:
        blur(7px);
}
.modal.show {
    display:
        flex;
}
.modal-box {
    width:
        min(720px,100%);
    max-height:
        91vh;
    overflow:
        auto;
    background:
        var(--cream);
    border-radius:
        20px;
    box-shadow:
        var(--shadow-large);
}
.modal-header {
    position:
        sticky;
    top:
        0;
    z-index:
        2;
    display:
        flex;
    align-items:
        center;
    justify-content:
        space-between;
    padding:
        22px 25px;
    background:
        rgba(250,247,240,.96);
    backdrop-filter:
        blur(12px);
    border-bottom:
        1px solid var(--border);
}
.modal-header h2 {
    font-size:
        23px;
}
.close-button {
    width:
        38px;
    height:
        38px;
    border:
        0;
    border-radius:
        9px;
    background:
        var(--tan-2);
    color:
        var(--black);
    font-size:
        23px;
    cursor:
        pointer;
}
.close-button:hover {
    background:
        var(--green-light);
    color:
        var(--green-dark);
}
.modal-content {
    padding:
        24px 25px 28px;
}
/* =========================================================
   EDIT TABS
========================================================= */
.tabs {
    display:
        flex;
    gap:
        6px;
    overflow-x:
        auto;
    margin-bottom:
        25px;
    padding-bottom:
        2px;
}
.tab {
    flex-shrink:
        0;
    border:
        0;
    border-radius:
        9px;
    background:
        var(--green-light);
    color:
        var(--green-dark);
    padding:
        10px 13px;
    font-size:
        13px;
    font-weight:
        800;
    cursor:
        pointer;
}
.tab.active {
    background:
        var(--green);
    color:
        white;
}
.editor {
    display:
        none;
}
.editor.active {
    display:
        block;
}
/* =========================================================
   FORM
========================================================= */
.form-group {
    margin-bottom:
        17px;
}
.form-label {
    display:
        block;
    margin-bottom:
        7px;
    font-size:
        13px;
    font-weight:
        850;
}
.form-help {
    display:
        block;
    margin-top:
        -10px;
    margin-bottom:
        15px;
    color:
        var(--gray);
    font-size:
        12px;
}
input,
textarea {
    width:
        100%;
    border:
        1px solid var(--border);
    border-radius:
        10px;
    background:
        white;
    color:
        var(--black);
    padding:
        12px 13px;
    outline:
        none;
    transition:
        border-color .2s ease,
        box-shadow .2s ease;
}
input:focus,
textarea:focus {
    border-color:
        var(--green);
    box-shadow:
        0 0 0 3px
        rgba(47,107,79,.12);
}
textarea {
    min-height:
        130px;
    resize:
        vertical;
}
input[type="file"] {
    padding:
        10px;
    background:
        var(--cream-2);
}
/* =========================================================
   UPLOAD BOX
========================================================= */
.upload-box {
    border:
        2px dashed var(--green);
    border-radius:
        14px;
    background:
        var(--green-pale);
    padding:
        28px 20px;
    text-align:
        center;
    margin-bottom:
        17px;
}
.upload-box strong {
    display:
        block;
    margin-bottom:
        5px;
}
.upload-box p {
    color:
        var(--gray);
    font-size:
        13px;
    margin-bottom:
        16px;
}
/* =========================================================
   EDITOR ROW
========================================================= */
.form-actions {
    display:
        flex;
    flex-wrap:
        wrap;
    gap:
        8px;
    margin-top:
        8px;
}
/* =========================================================
   STATUS
========================================================= */
.status {
    display:
        none;
    margin-top:
        18px;
    padding:
        12px 14px;
    border-radius:
        10px;
    background:
        var(--green-light);
    color:
        var(--green-dark);
    font-size:
        13px;
    font-weight:
        700;
}
.status.show {
    display:
        block;
}
/* =========================================================
   LIGHTBOX
========================================================= */
.lightbox {
    position:
        fixed;
    inset:
        0;
    z-index:
        4000;
    display:
        none;
    align-items:
        center;
    justify-content:
        center;
    padding:
        20px;
    background:
        rgba(17,17,17,.90);
}
.lightbox.show {
    display:
        flex;
}
.lightbox img {
    max-width:
        min(1100px,94vw);
    max-height:
        88vh;
    object-fit:
        contain;
    border-radius:
        12px;
    box-shadow:
        0 25px 80px
        rgba(0,0,0,.5);
}
.lightbox-close {
    position:
        absolute;
    top:
        20px;
    right:
        20px;
    width:
        44px;
    height:
        44px;
    border:
        0;
    border-radius:
        50%;
    background:
        rgba(255,255,255,.14);
    color:
        white;
    font-size:
        25px;
    cursor:
        pointer;
}
/* =========================================================
   FOOTER
========================================================= */
footer {
    border-top:
        1px solid var(--border);
    padding:
        32px 0 90px;
    color:
        var(--gray);
    font-size:
        13px;
}
.footer-inner {
    display:
        flex;
    align-items:
        center;
    justify-content:
        space-between;
    gap:
        15px;
}
.footer-name {
    color:
        var(--black);
    font-weight:
        850;
}
/* =========================================================
   RESPONSIVE
========================================================= */
@media (max-width: 900px) {
    .desktop-nav {
        display:
            none;
    }
    .menu-button {
        display:
            block;
    }
    .hero {
        grid-template-columns:
            1fr;
        gap:
            55px;
        text-align:
            center;
    }
    .hero-copy {
        margin:
            0 auto;
    }
    .hero-description {
        margin:
            0 auto 28px;
    }
    .hero-actions {
        justify-content:
            center;
    }
    .hero-photo-frame {
        width:
            min(350px,80vw);
    }
    .quick-grid {
        grid-template-columns:
            1fr;
    }
}
@media (max-width: 700px) {
    .container {
        width:
            min(
                calc(100% - 28px),
                1180px
            );
    }
    .home {
        padding:
            50px 0 70px;
    }
    .hero {
        min-height:
            auto;
    }
    .hero-title {
        font-size:
            clamp(57px,18vw,90px);
        letter-spacing:
            -5px;
    }
    .section {
        padding:
            45px 0 70px;
    }
    .section-title {
        font-size:
            clamp(42px,14vw,65px);
        letter-spacing:
            -3px;
    }
    .photo-grid {
        grid-template-columns:
            repeat(2,1fr);
        gap:
            10px;
    }
    .document-grid {
        grid-template-columns:
            1fr;
    }
    .article {
        grid-template-columns:
            1fr;
        gap:
            15px;
    }
    .article-link {
        justify-self:
            start;
    }
    .photo-toolbar {
        align-items:
            flex-start;
        flex-direction:
            column;
    }
    .modal-content {
        padding:
            20px;
    }
}
@media (max-width: 430px) {
    .photo-grid {
        grid-template-columns:
            1fr;
    }
    .photo-card {
        aspect-ratio:
            4 / 3;
    }
    .edit-button {
        right:
            14px;
        bottom:
            14px;
    }
    .footer-inner {
        flex-direction:
            column;
        align-items:
            flex-start;
    }
}
/* =========================================================
   REDUCED MOTION
========================================================= */
@media (prefers-reduced-motion: reduce) {
    * {
        scroll-behavior:
            auto !important;
        transition:
            none !important;
        animation:
            none !important;
    }
}
</style>
</head>
<body>
<!-- =======================================================
     HEADER
======================================================= -->
<header class="site-header">
    <div class="container header-inner">
        <a
            href="#"
            class="logo"
            id="logoButton"
        >
            Graysen
        </a>
        <nav
            class="desktop-nav"
            aria-label="Main navigation"
        >
            <button
                class="nav-button active"
                data-page="home"
            >
                Home
            </button>
            <button
                class="nav-button"
                data-page="photography"
            >
                Photography
            </button>
            <button
                class="nav-button"
                data-page="research"
            >
                Research
            </button>
            <button
                class="nav-button"
                data-page="newspaper"
            >
                Newspaper
            </button>
        </nav>
        <button
            class="menu-button"
            id="menuButton"
            aria-label="Open menu"
            aria-expanded="false"
        >
            ☰
        </button>
    </div>
    <nav
        class="mobile-nav"
        id="mobileNav"
        aria-label="Mobile navigation"
    >
        <button
            data-page="home"
        >
            Home
        </button>
        <button
            data-page="photography"
        >
            Photography
        </button>
        <button
            data-page="research"
        >
            Research
        </button>
        <button
            data-page="newspaper"
        >
            Newspaper
        </button>
    </nav>
</header>
<!-- =======================================================
     MAIN
======================================================= -->
<main>
<!-- =======================================================
     HOME PAGE
======================================================= -->
<section
    class="page active"
    id="home"
>
    <div class="home">
        <div class="container">
            <div class="hero">
                <div class="hero-copy">
                    <div class="eyebrow">
                        Welcome
                    </div>
                    <h1
                        class="hero-title"
                        id="heroName"
                    >
                        Graysen<span class="accent">.</span>
                    </h1>
                    <p
                        class="hero-description"
                        id="bioText"
                    >
                        Welcome to my portfolio.
                        Here you'll find my photography,
                        research, writing, and projects.
                    </p>
                    <div class="hero-actions">
                        <button
                            class="button"
                            data-go="photography"
                        >
                            View Photography →
                        </button>
                        <button
                            class="button secondary"
                            data-go="newspaper"
                        >
                            Read My Work
                        </button>
                    </div>
                </div>
                <div class="hero-photo-wrap">
                    <div class="hero-photo-frame">
                        <img
                            class="hero-photo hidden"
                            id="profileImage"
                            alt="Graysen"
                        >
                        <div
                            class="hero-photo-placeholder"
                            id="profilePlaceholder"
                        >
                            <div>
                                <strong>
                                    Your photo
                                </strong>
                                <span>
                                    Add a profile photo
                                    through EDIT.
                                </span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <!-- QUICK LINKS -->
    <div class="quick-section">
        <div class="container">
            <div class="quick-grid">
                <div
                    class="quick-card"
                    data-go="photography"
                >
                    <div class="quick-number">
                        01
                    </div>
                    <h3>
                        Photography
                    </h3>
                    <p>
                        A visual collection of
                        photographs and projects.
                    </p>
                </div>
                <div
                    class="quick-card"
                    data-go="research"
                >
                    <div class="quick-number">
                        02
                    </div>
                    <h3>
                        Research
                    </h3>
                    <p>
                        Research projects,
                        documents, and work.
                    </p>
                </div>
                <div
                    class="quick-card"
                    data-go="newspaper"
                >
                    <div class="quick-number">
                        03
                    </div>
                    <h3>
                        Newspaper
                    </h3>
                    <p>
                        Articles, writing,
                        and published work.
                    </p>
                </div>
            </div>
        </div>
    </div>
</section>
<!-- =======================================================
     PHOTOGRAPHY PAGE
======================================================= -->
<section
    class="page"
    id="photography"
>
    <div class="section">
        <div class="container">
            <div class="section-heading">
                <div class="eyebrow">
                    Portfolio
                </div>
                <h2 class="section-title">
                    Photography
                </h2>
                <p class="section-subtitle">
                    A collection of photographs
                    and visual work.
                </p>
                <div class="green-line"></div>
            </div>
            <div class="photo-toolbar">
                <div
                    class="photo-count"
                    id="photoCount"
                >
                    0 photos
                </div>
                <button
                    class="button small secondary"
                    id="photoEditShortcut"
                >
                    Add Photos
                </button>
            </div>
            <div
                class="photo-grid"
                id="photoGrid"
            >
                <div class="empty-state">
                    <div class="empty-icon">
                        +
                    </div>
                    <h3>
                        No photos yet
                    </h3>
                    <p>
                        Use EDIT to add your
                        first photographs.
                    </p>
                </div>
            </div>
        </div>
    </div>
</section>
<!-- =======================================================
     RESEARCH PAGE
======================================================= -->
<section
    class="page"
    id="research"
>
    <div class="section">
        <div class="container">
            <div class="section-heading">
                <div class="eyebrow">
                    Work
                </div>
                <h2 class="section-title">
                    Research
                </h2>
                <p class="section-subtitle">
                    Research projects, documents,
                    and written work.
                </p>
                <div class="green-line"></div>
            </div>
            <div
                class="document-grid"
                id="documentGrid"
            >
                <div class="empty-state">
                    <div class="empty-icon">
                        +
                    </div>
                    <h3>
                        No research yet
                    </h3>
                    <p>
                        Add a research project
                        through EDIT.
                    </p>
                </div>
            </div>
        </div>
    </div>
</section>
<!-- =======================================================
     NEWSPAPER PAGE
======================================================= -->
<section
    class="page"
    id="newspaper"
>
    <div class="section">
        <div class="container">
            <div class="section-heading">
                <div class="eyebrow">
                    Writing
                </div>
                <h2 class="section-title">
                    Newspaper
                </h2>
                <p class="section-subtitle">
                    Articles, stories, and
                    published writing.
                </p>
                <div class="green-line"></div>
            </div>
            <div
                class="article-list"
                id="articleList"
            >
                <div class="empty-state">
                    <div class="empty-icon">
                        +
                    </div>
                    <h3>
                        No articles yet
                    </h3>
                    <p>
                        Add an article through
                        EDIT.
                    </p>
                </div>
            </div>
        </div>
    </div>
</section>
</main>
<!-- =======================================================
     FOOTER
======================================================= -->
<footer>
    <div class="container footer-inner">
        <div>
            © <span id="year"></span>
            <span class="footer-name">
                Graysen
            </span>
        </div>
        <div>
            Personal Portfolio
        </div>
    </div>
</footer>
<!-- =======================================================
     EDIT BUTTON
======================================================= -->
<button
    class="edit-button"
    id="editButton"
>
    ✎ EDIT
</button>
<!-- =======================================================
     EDIT MODAL
======================================================= -->
<div
    class="modal"
    id="editModal"
    role="dialog"
    aria-modal="true"
    aria-labelledby="editTitle"
>
    <div class="modal-box">
        <div class="modal-header">
            <h2 id="editTitle">
                Edit Website
            </h2>
            <button
                class="close-button"
                id="closeModal"
                aria-label="Close"
            >
                ×
            </button>
        </div>
        <div class="modal-content">
            <!-- TABS -->
            <div class="tabs">
                <button
                    class="tab active"
                    data-editor="homeEditor"
                >
                    Home
                </button>
                <button
                    class="tab"
                    data-editor="photoEditor"
                >
                    Photos
                </button>
                <button
                    class="tab"
                    data-editor="researchEditor"
                >
                    Research
                </button>
                <button
                    class="tab"
                    data-editor="newspaperEditor"
                >
                    Newspaper
                </button>
            </div>
            <!-- =================================================
                 HOME EDITOR
            ================================================== -->
            <div
                class="editor active"
                id="homeEditor"
            >
                <div class="form-group">
                    <label
                        class="form-label"
                        for="bioInput"
                    >
                        About Me
                    </label>
                    <textarea
                        id="bioInput"
                        placeholder="Write something about yourself..."
                    ></textarea>
                </div>
                <div class="form-group">
                    <label
                        class="form-label"
                        for="profileInput"
                    >
                        Profile Photo
                    </label>
                    <span class="form-help">
                        The photo is automatically
                        compressed before being saved.
                    </span>
                    <input
                        type="file"
                        id="profileInput"
                        accept="image/*"
                    >
                </div>
                <div class="form-actions">
                    <button
                        class="button"
                        id="saveHome"
                    >
                        Save Home
                    </button>
                </div>
            </div>
            <!-- =================================================
                 PHOTO EDITOR
            ================================================== -->
            <div
                class="editor"
                id="photoEditor"
            >
                <div class="upload-box">
                    <strong>
                        Add Photography
                    </strong>
                    <p>
                        Up to 25 photos.
                        Large images are automatically
                        resized and compressed.
                    </p>
                    <input
                        type="file"
                        id="photoInput"
                        accept="image/*"
                        multiple
                    >
                </div>
                <div class="form-actions">
                    <button
                        class="button outline"
                        id="clearPhotos"
                    >
                        Clear All Photos
                    </button>
                </div>
            </div>
            <!-- =================================================
                 RESEARCH EDITOR
            ================================================== -->
            <div
                class="editor"
                id="researchEditor"
            >
                <div class="form-group">
                    <label
                        class="form-label"
                        for="researchTitle"
                    >
                        Research Title
                    </label>
                    <input
                        id="researchTitle"
                        type="text"
                        placeholder="Example: Research Project"
                    >
                </div>
                <div class="form-group">
                    <label
                        class="form-label"
                        for="researchDescription"
                    >
                        Description
                    </label>
                    <textarea
                        id="researchDescription"
                        placeholder="Describe the research..."
                    ></textarea>
                </div>
                <div class="form-group">
                    <label
                        class="form-label"
                        for="researchFile"
                    >
                        Document
                    </label>
                    <input
                        type="file"
                        id="researchFile"
                    >
                </div>
                <div class="form-actions">
                    <button
                        class="button"
                        id="saveResearch"
                    >
                        Add Research
                    </button>
                </div>
            </div>
            <!-- =================================================
                 NEWSPAPER EDITOR
            ================================================== -->
            <div
                class="editor"
                id="newspaperEditor"
            >
                <div class="form-group">
                    <label
                        class="form-label"
                        for="articleTitle"
                    >
                        Article Title
                    </label>
                    <input
                        id="articleTitle"
                        type="text"
                        placeholder="Article title"
                    >
                </div>
                <div class="form-group">
                    <label
                        class="form-label"
                        for="articleDescription"
                    >
                        Description
                    </label>
                    <textarea
                        id="articleDescription"
                        placeholder="Short description of the article..."
                    ></textarea>
                </div>
                <div class="form-group">
                    <label
                        class="form-label"
                        for="articleURL"
                    >
                        Article Link
                    </label>
                    <input
                        id="articleURL"
                        type="url"
                        placeholder="https://example.com"
                    >
                </div>
                <div class="form-actions">
                    <button
                        class="button"
                        id="saveArticle"
                    >
                        Add Article
                    </button>
                </div>
            </div>
            <div
                class="status"
                id="status"
            ></div>
        </div>
    </div>
</div>
<!-- =======================================================
     PHOTO LIGHTBOX
======================================================= -->
<div
    class="lightbox"
    id="lightbox"
>
    <button
        class="lightbox-close"
        id="lightboxClose"
        aria-label="Close photo"
    >
        ×
    </button>
    <img
        id="lightboxImage"
        alt="Expanded photograph"
    >
</div>
<script>
/* =========================================================
   SETTINGS
========================================================= */
const EDIT_CODE = "4547";
const MAX_PHOTOS = 25;
const DATABASE_NAME =
    "GraysenPortfolioDatabase";
const DATABASE_VERSION = 2;
/* =========================================================
   GLOBAL DATABASE
========================================================= */
let db = null;
/* =========================================================
   OPEN DATABASE
========================================================= */
const databaseRequest =
    indexedDB.open(
        DATABASE_NAME,
        DATABASE_VERSION
    );
databaseRequest.onupgradeneeded =
    function(event) {
        const database =
            event.target.result;
        if (
            !database.objectStoreNames.contains(
                "photos"
            )
        ) {
            database.createObjectStore(
                "photos",
                {
                    keyPath: "id",
                    autoIncrement: true
                }
            );
        }
        if (
            !database.objectStoreNames.contains(
                "research"
            )
        ) {
            database.createObjectStore(
                "research",
                {
                    keyPath: "id",
                    autoIncrement: true
                }
            );
        }
        if (
            !database.objectStoreNames.contains(
                "articles"
            )
        ) {
            database.createObjectStore(
                "articles",
                {
                    keyPath: "id",
                    autoIncrement: true
                }
            );
        }
        if (
            !database.objectStoreNames.contains(
                "settings"
            )
        ) {
            database.createObjectStore(
                "settings",
                {
                    keyPath: "key"
                }
            );
        }
    };
databaseRequest.onsuccess =
    function(event) {
        db =
            event.target.result;
        loadEverything();
    };
databaseRequest.onerror =
    function() {
        console.error(
            "Database could not be opened."
        );
    };
/* =========================================================
   DATABASE STORE
========================================================= */
function store(
    storeName,
    mode = "readonly"
) {
    return db
        .transaction(
            storeName,
            mode
        )
        .objectStore(
            storeName
        );
}
/* =========================================================
   GET ALL
========================================================= */
function getAllItems(
    storeName
) {
    return new Promise(
        (resolve, reject) => {
            const request =
                store(
                    storeName
                ).getAll();
            request.onsuccess =
                () => resolve(
                    request.result
                );
            request.onerror =
                () => reject(
                    request.error
                );
        }
    );
}
/* =========================================================
   ADD ITEM
========================================================= */
function addItem(
    storeName,
    item
) {
    return new Promise(
        (resolve, reject) => {
            const request =
                store(
                    storeName,
                    "readwrite"
                ).add(item);
            request.onsuccess =
                () => resolve(
                    request.result
                );
            request.onerror =
                () => reject(
                    request.error
                );
        }
    );
}
/* =========================================================
   PUT SETTING
========================================================= */
function saveSetting(
    key,
    value
) {
    return new Promise(
        (resolve, reject) => {
            const request =
                store(
                    "settings",
                    "readwrite"
                ).put({
                    key: key,
                    value: value
                });
            request.onsuccess =
                () => resolve();
            request.onerror =
                () => reject(
                    request.error
                );
        }
    );
}
/* =========================================================
   GET SETTING
========================================================= */
function getSetting(
    key
) {
    return new Promise(
        (resolve, reject) => {
            const request =
                store(
                    "settings"
                ).get(key);
            request.onsuccess =
                () => {
                    resolve(
                        request.result
                            ? request.result.value
                            : null
                    );
                };
            request.onerror =
                () => reject(
                    request.error
                );
        }
    );
}
/* =========================================================
   DELETE ALL
========================================================= */
function clearStore(
    storeName
) {
    return new Promise(
        (resolve, reject) => {
            const request =
                store(
                    storeName,
                    "readwrite"
                ).clear();
            request.onsuccess =
                () => resolve();
            request.onerror =
                () => reject(
                    request.error
                );
        }
    );
}
/* =========================================================
   IMAGE COMPRESSION
========================================================= */
function compressImage(
    file,
    maxSize = 1200,
    quality = 0.55
) {
    return new Promise(
        (resolve, reject) => {
            const reader =
                new FileReader();
            reader.onload =
                function(event) {
                    const image =
                        new Image();
                    image.onload =
                        function() {
                            let width =
                                image.width;
                            let height =
                                image.height;
                            if (
                                width > maxSize ||
                                height > maxSize
                            ) {
                                const ratio =
                                    Math.min(
                                        maxSize / width,
                                        maxSize / height
                                    );
                                width =
                                    Math.round(
                                        width * ratio
                                    );
                                height =
                                    Math.round(
                                        height * ratio
                                    );
                            }
                            const canvas =
                                document.createElement(
                                    "canvas"
                                );
                            canvas.width =
                                width;
                            canvas.height =
                                height;
                            const context =
                                canvas.getContext(
                                    "2d"
                                );
                            context.drawImage(
                                image,
                                0,
                                0,
                                width,
                                height
                            );
                            canvas.toBlob(
                                function(blob) {
                                    if (!blob) {
                                        reject(
                                            new Error(
                                                "Image compression failed."
                                            )
                                        );
                                        return;
                                    }
                                    resolve(blob);
                                },
                                "image/jpeg",
                                quality
                            );
                        };
                    image.onerror =
                        function() {
                            reject(
                                new Error(
                                    "Image could not be loaded."
                                )
                            );
                        };
                    image.src =
                        event.target.result;
                };
            reader.onerror =
                function() {
                    reject(
                        new Error(
                            "File could not be read."
                        )
                    );
                };
            reader.readAsDataURL(file);
        }
    );
}
/* =========================================================
   NAVIGATION
========================================================= */
const allNavigationButtons =
    document.querySelectorAll(
        "[data-page]"
    );
function showPage(
    pageName
) {
    document
        .querySelectorAll(".page")
        .forEach(
            page => {
                page.classList.remove(
                    "active"
                );
                if (
                    page.id === pageName
                ) {
                    page.classList.add(
                        "active"
                    );
                }
            }
        );
    document
        .querySelectorAll(
            ".nav-button, .mobile-nav button"
        )
        .forEach(
            button => {
                button.classList.toggle(
                    "active",
                    button.dataset.page ===
                        pageName
                );
            }
        );
    document
        .getElementById(
            "mobileNav"
        )
        .classList.remove(
            "open"
        );
    document
        .getElementById(
            "menuButton"
        )
        .setAttribute(
            "aria-expanded",
            "false"
        );
    window.scrollTo({
        top: 0,
        behavior: "smooth"
    });
}
allNavigationButtons.forEach(
    button => {
        button.addEventListener(
            "click",
            function() {
                showPage(
                    button.dataset.page
                );
            }
        );
    }
);
/* =========================================================
   LOGO
========================================================= */
document
    .getElementById("logoButton")
    .addEventListener(
        "click",
        function(event) {
            event.preventDefault();
            showPage("home");
        }
    );
/* =========================================================
   QUICK LINKS
========================================================= */
document
    .querySelectorAll(
        "[data-go]"
    )
    .forEach(
        element => {
            element.addEventListener(
                "click",
                function() {
                    showPage(
                        element.dataset.go
                    );
                }
            );
        }
    );
/* =========================================================
   MOBILE MENU
========================================================= */
document
    .getElementById("menuButton")
    .addEventListener(
        "click",
        function() {
            const menu =
                document.getElementById(
                    "mobileNav"
                );
            const isOpen =
                menu.classList.toggle(
                    "open"
                );
            this.setAttribute(
                "aria-expanded",
                isOpen
            );
        }
    );
/* =========================================================
   EDIT MODAL
========================================================= */
const editButton =
    document.getElementById(
        "editButton"
    );
const editModal =
    document.getElementById(
        "editModal"
    );
const closeModal =
    document.getElementById(
        "closeModal"
    );
editButton.addEventListener(
    "click",
    function() {
        const enteredCode =
            prompt(
                "Enter your edit code:"
            );
        if (
            enteredCode === EDIT_CODE
        ) {
            editModal.classList.add(
                "show"
            );
            document.body.style.overflow =
                "hidden";
        } else if (
            enteredCode !== null
        ) {
            alert(
                "Incorrect code."
            );
        }
    }
);
function closeEditor() {
    editModal.classList.remove(
        "show"
    );
    document.body.style.overflow =
        "";
}
closeModal.addEventListener(
    "click",
    closeEditor
);
editModal.addEventListener(
    "click",
    function(event) {
        if (
            event.target === editModal
        ) {
            closeEditor();
        }
    }
);
/* =========================================================
   EDIT TABS
========================================================= */
document
    .querySelectorAll(".tab")
    .forEach(
        tab => {
            tab.addEventListener(
                "click",
                function() {
                    const target =
                        tab.dataset.editor;
                    document
                        .querySelectorAll(
                            ".tab"
                        )
                        .forEach(
                            item =>
                                item.classList
                                    .remove(
                                        "active"
                                    )
                        );
                    document
                        .querySelectorAll(
                            ".editor"
                        )
                        .forEach(
                            editor =>
                                editor.classList
                                    .remove(
                                        "active"
                                    )
                        );
                    tab.classList.add(
                        "active"
                    );
                    document
                        .getElementById(
                            target
                        )
                        .classList.add(
                            "active"
                        );
                }
            );
        }
    );
/* =========================================================
   PHOTO EDIT SHORTCUT
========================================================= */
document
    .getElementById(
        "photoEditShortcut"
    )
    .addEventListener(
        "click",
        function() {
            const code =
                prompt(
                    "Enter your edit code:"
                );
            if (
                code === EDIT_CODE
            ) {
                editModal.classList.add(
                    "show"
                );
                document.body.style.overflow =
                    "hidden";
                document
                    .querySelectorAll(
                        ".tab"
                    )
                    .forEach(
                        tab =>
                            tab.classList
                                .remove(
                                    "active"
                                )
                    );
                document
                    .querySelectorAll(
                        ".editor"
                    )
                    .forEach(
                        editor =>
                            editor.classList
                                .remove(
                                    "active"
                                )
                    );
                document
                    .querySelector(
                        '[data-editor="photoEditor"]'
                    )
                    .classList.add(
                        "active"
                    );
                document
                    .getElementById(
                        "photoEditor"
                    )
                    .classList.add(
                        "active"
                    );
            }
        }
    );
/* =========================================================
   HOME SAVE
========================================================= */
document
    .getElementById(
        "saveHome"
    )
    .addEventListener(
        "click",
        async function() {
            try {
                const bio =
                    document
                        .getElementById(
                            "bioInput"
                        )
                        .value
                        .trim();
                await saveSetting(
                    "bio",
                    bio
                );
                const file =
                    document
                        .getElementById(
                            "profileInput"
                        )
                        .files[0];
                if (file) {
                    const compressed =
                        await compressImage(
                            file,
                            1200,
                            0.60
                        );
                    const reader =
                        new FileReader();
                    await new Promise(
                        resolve => {
                            reader.onload =
                                async function() {
                                    await saveSetting(
                                        "profileImage",
                                        reader.result
                                    );
                                    resolve();
                                };
                            reader.readAsDataURL(
                                compressed
                            );
                        }
                    );
                }
                await loadHome();
                showStatus(
                    "Home page saved successfully."
                );
            } catch(error) {
                console.error(error);
                showStatus(
                    "Something went wrong while saving."
                );
            }
        }
    );
/* =========================================================
   LOAD HOME
========================================================= */
async function loadHome() {
    const bio =
        await getSetting(
            "bio"
        );
    const profileImage =
        await getSetting(
            "profileImage"
        );
    if (
        bio !== null &&
        bio !== ""
    ) {
        document
            .getElementById(
                "bioText"
            )
            .textContent =
            bio;
        document
            .getElementById(
                "bioInput"
            )
            .value =
            bio;
    }
    if (profileImage) {
        const image =
            document.getElementById(
                "profileImage"
            );
        image.src =
            profileImage;
        image.classList.remove(
            "hidden"
        );
        document
            .getElementById(
                "profilePlaceholder"
            )
            .classList.add(
                "hidden"
            );
    }
}
/* =========================================================
   ADD PHOTOS
========================================================= */
document
    .getElementById(
        "photoInput"
    )
    .addEventListener(
        "change",
        async function(event) {
            const files =
                Array.from(
                    event.target.files
                );
            if (
                files.length === 0
            ) {
                return;
            }
            const existing =
                await getAllItems(
                    "photos"
                );
            const remaining =
                MAX_PHOTOS -
                existing.length;
            if (
                remaining <= 0
            ) {
                alert(
                    "You already have 25 photos."
                );
                event.target.value =
                    "";
                return;
            }
            if (
                files.length > remaining
            ) {
                alert(
                    `You can only add ${remaining} more photo(s).`
                );
                event.target.value =
                    "";
                return;
            }
            let added =
                0;
            for (
                const file of files
            ) {
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
                            image:
                                compressed,
                            created:
                                Date.now()
                        }
                    );
                    added++;
                } catch(error) {
                    console.error(
                        error
                    );
                }
            }
            event.target.value =
                "";
            await loadPhotos();
            showStatus(
                `${added} photo${added === 1 ? "" : "s"} added.`
            );
        }
    );
/* =========================================================
   LOAD PHOTOS
========================================================= */
async function loadPhotos() {
    const grid =
        document.getElementById(
            "photoGrid"
        );
    const count =
        document.getElementById(
            "photoCount"
        );
    const photos =
        await getAllItems(
            "photos"
        );
    count.textContent =
        `${photos.length} ${
            photos.length === 1
                ? "photo"
                : "photos"
        }`;
    grid.innerHTML =
        "";
    if (
        photos.length === 0
    ) {
        grid.innerHTML = `
            <div class="empty-state">
                <div class="empty-icon">
                    +
                </div>
                <h3>
                    No photos yet
                </h3>
                <p>
                    Use EDIT to add your
                    first photographs.
                </p>
            </div>
        `;
        return;
    }
    photos.forEach(
        (photo, index) => {
            const card =
                document.createElement(
                    "div"
                );
            card.className =
                "photo-card";
            const image =
                document.createElement(
                    "img"
                );
            image.alt =
                `Photography ${index + 1}`;
            const objectURL =
                URL.createObjectURL(
                    photo.image
                );
            image.src =
                objectURL;
            image.onload =
                function() {
                    URL.revokeObjectURL(
                        objectURL
                    );
                };
            const overlay =
                document.createElement(
                    "div"
                );
            overlay.className =
                "photo-overlay";
            overlay.textContent =
                "View photo";
            card.appendChild(
                image
            );
            card.appendChild(
                overlay
            );
            card.addEventListener(
                "click",
                function() {
                    openLightbox(
                        photo.image
                    );
                }
            );
            grid.appendChild(
                card
            );
        }
    );
}
/* =========================================================
   LIGHTBOX
========================================================= */
const lightbox =
    document.getElementById(
        "lightbox"
    );
const lightboxImage =
    document.getElementById(
        "lightboxImage"
    );
function openLightbox(
    blob
) {
    const url =
        URL.createObjectURL(
            blob
        );
    lightboxImage.src =
        url;
    lightboxImage.onload =
        function() {
            lightbox.classList.add(
                "show"
            );
            document.body.style.overflow =
                "hidden";
        };
    lightboxImage.dataset.url =
        url;
}
function closeLightbox() {
    lightbox.classList.remove(
        "show"
    );
    document.body.style.overflow =
        "";
    if (
        lightboxImage.dataset.url
    ) {
        URL.revokeObjectURL(
            lightboxImage.dataset.url
        );
        lightboxImage.dataset.url =
            "";
    }
    lightboxImage.src =
        "";
}
document
    .getElementById(
        "lightboxClose"
    )
    .addEventListener(
        "click",
        closeLightbox
    );
lightbox.addEventListener(
    "click",
    function(event) {
        if (
            event.target === lightbox
        ) {
            closeLightbox();
        }
    }
);
/* =========================================================
   CLEAR PHOTOS
========================================================= */
document
    .getElementById(
        "clearPhotos"
    )
    .addEventListener(
        "click",
        async function() {
            const photos =
                await getAllItems(
                    "photos"
                );
            if (
                photos.length === 0
            ) {
                showStatus(
                    "There are no photos to clear."
                );
                return;
            }
            const confirmed =
                confirm(
                    "Delete all photos? This cannot be undone."
                );
            if (!confirmed) {
                return;
            }
            await clearStore(
                "photos"
            );
            await loadPhotos();
            showStatus(
                "All photos were removed."
            );
        }
    );
/* =========================================================
   ADD RESEARCH
========================================================= */
document
    .getElementById(
        "saveResearch"
    )
    .addEventListener(
        "click",
        async function() {
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
                    .files[0] ||
                null;
            if (
                !title
            ) {
                alert(
                    "Please enter a research title."
                );
                return;
            }
            await addItem(
                "research",
                {
                    title:
                        title,
                    description:
                        description,
                    file:
                        file,
                    created:
                        Date.now()
                }
            );
            document
                .getElementById(
                    "researchTitle"
                )
                .value =
                "";
            document
                .getElementById(
                    "researchDescription"
                )
                .value =
                "";
            document
                .getElementById(
                    "researchFile"
                )
                .value =
                "";
            await loadResearch();
            showStatus(
                "Research project added."
            );
        }
    );
/* =========================================================
   LOAD RESEARCH
========================================================= */
async function loadResearch() {
    const grid =
        document.getElementById(
            "documentGrid"
        );
    const documents =
        await getAllItems(
            "research"
        );
    grid.innerHTML =
        "";
    if (
        documents.length === 0
    ) {
        grid.innerHTML = `
            <div class="empty-state">
                <div class="empty-icon">
                    +
                </div>
                <h3>
                    No research yet
                </h3>
                <p>
                    Add a research project
                    through EDIT.
                </p>
            </div>
        `;
        return;
    }
    documents.forEach(
        documentItem => {
            const card =
                document.createElement(
                    "div"
                );
            card.className =
                "document-card";
            const top =
                document.createElement(
                    "div"
                );
            top.className =
                "document-top";
            const text =
                document.createElement(
                    "div"
                );
            const title =
                document.createElement(
                    "h3"
                );
            title.textContent =
                documentItem.title;
            text.appendChild(
                title
            );
            const icon =
                document.createElement(
                    "div"
                );
            icon.className =
                "document-icon";
            icon.textContent =
                "R";
            top.appendChild(
                text
            );
            top.appendChild(
                icon
            );
            const description =
                document.createElement(
                    "p"
                );
            description.textContent =
                documentItem.description ||
                "Research project.";
            card.appendChild(
                top
            );
            card.appendChild(
                description
            );
            if (
                documentItem.file
            ) {
                const link =
                    document.createElement(
                        "a"
                    );
                link.className =
                    "button small";
                link.textContent =
                    "Open Document →";
                link.href =
                    URL.createObjectURL(
                        documentItem.file
                    );
                link.target =
                    "_blank";
                link.rel =
                    "noopener noreferrer";
                card.appendChild(
                    link
                );
            }
            grid.appendChild(
                card
            );
        }
    );
}
/* =========================================================
   ADD ARTICLE
========================================================= */
document
    .getElementById(
        "saveArticle"
    )
    .addEventListener(
        "click",
        async function() {
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
            if (
                !title
            ) {
                alert(
                    "Please enter an article title."
                );
                return;
            }
            await addItem(
                "articles",
                {
                    title:
                        title,
                    description:
                        description,
                    url:
                        url,
                    created:
                        Date.now()
                }
            );
            document
                .getElementById(
                    "articleTitle"
                )
                .value =
                "";
            document
                .getElementById(
                    "articleDescription"
                )
                .value =
                "";
            document
                .getElementById(
                    "articleURL"
                )
                .value =
                "";
            await loadArticles();
            showStatus(
                "Article added."
            );
        }
    );
/* =========================================================
   LOAD ARTICLES
========================================================= */
async function loadArticles() {
    const list =
        document.getElementById(
            "articleList"
        );
    const articles =
        await getAllItems(
            "articles"
        );
    list.innerHTML =
        "";
    if (
        articles.length === 0
    ) {
        list.innerHTML = `
            <div class="empty-state">
                <div class="empty-icon">
                    +
                </div>
                <h3>
                    No articles yet
                </h3>
                <p>
                    Add an article through
                    EDIT.
                </p>
            </div>
        `;
        return;
    }
    articles.forEach(
        article => {
            const item =
                document.createElement(
                    "article"
                );
            item.className =
                "article";
            const text =
                document.createElement(
                    "div"
                );
            const label =
                document.createElement(
                    "div"
                );
            label.className =
                "article-label";
            label.textContent =
                "Article";
            const title =
                document.createElement(
                    "h3"
                );
            title.textContent =
                article.title;
            text.appendChild(
                label
            );
            text.appendChild(
                title
            );
            if (
                article.description
            ) {
                const description =
                    document.createElement(
                        "p"
                    );
                description.textContent =
                    article.description;
                text.appendChild(
                    description
                );
            }
            item.appendChild(
                text
            );
            if (
                article.url
            ) {
                const link =
                    document.createElement(
                        "a"
                    );
                link.className =
                    "button small article-link";
                link.textContent =
                    "Read Article →";
                link.href =
                    article.url;
                link.target =
                    "_blank";
                link.rel =
                    "noopener noreferrer";
                item.appendChild(
                    link
                );
            }
            list.appendChild(
                item
            );
        }
    );
}
/* =========================================================
   STATUS MESSAGE
========================================================= */
let statusTimer = null;
function showStatus(
    message
) {
    const status =
        document.getElementById(
            "status"
        );
    status.textContent =
        message;
    status.classList.add(
        "show"
    );
    clearTimeout(
        statusTimer
    );
    statusTimer =
        setTimeout(
            function() {
                status.classList.remove(
                    "show"
                );
            },
            3500
        );
}
/* =========================================================
   ESCAPE KEY
========================================================= */
document.addEventListener(
    "keydown",
    function(event) {
        if (
            event.key === "Escape"
        ) {
            if (
                lightbox.classList.contains(
                    "show"
                )
            ) {
                closeLightbox();
            } else if (
                editModal.classList.contains(
                    "show"
                )
            ) {
                closeEditor();
            }
        }
    }
);
/* =========================================================
   LOAD EVERYTHING
========================================================= */
async function loadEverything() {
    try {
        await loadHome();
        await loadPhotos();
        await loadResearch();
        await loadArticles();
        document
            .getElementById(
                "year"
            )
            .textContent =
            new Date()
                .getFullYear();
    } catch(error) {
        console.error(
            "Could not load portfolio:",
            error
        );
    }
}
/* =========================================================
   START
========================================================= */
document
    .getElementById(
        "year"
    )
    .textContent =
    new Date()
        .getFullYear();
</script>
</body>
</html>