
(function () {
    'use strict';

    const css = `
    /* =====================================================
       GITHUB HACKER CRT ULTRA
       ===================================================== */

    :root {
        --bg: #010403;
        --panel: #030b07;
        --panel2: #06120c;

        --green: #00ff66;
        --green2: #00c853;
        --cyan: #00ffe1;

        --white: #d9ffe8;
        --muted: #57816a;

        --line: rgba(0,255,102,.18);
        --glow: rgba(0,255,102,.35);
    }

    /* =====================================================
       BASE
       ===================================================== */

    html,
    body {
        background:
            radial-gradient(
                circle at 50% -20%,
                rgba(0,255,102,.12),
                transparent 40%
            ),
            radial-gradient(
                circle at 100% 100%,
                rgba(0,255,225,.06),
                transparent 35%
            ),
            var(--bg) !important;

        color: var(--white) !important;
    }

    body {
        font-family:
            "JetBrains Mono",
            "Fira Code",
            "Cascadia Code",
            "Courier New",
            monospace !important;
    }

    /* =====================================================
       CRT SCANLINES
       ===================================================== */

    body::before {
        content: "";
        position: fixed;
        inset: 0;

        pointer-events: none;

        z-index: 999998;

        background:
            repeating-linear-gradient(
                0deg,
                rgba(0,255,102,.025) 0px,
                rgba(0,255,102,.025) 1px,
                transparent 1px,
                transparent 4px
            );

        opacity: .45;
    }

    /* =====================================================
       CRT VIGNETTE
       ===================================================== */

    body::after {
        content: "";

        position: fixed;
        inset: 0;

        pointer-events: none;

        z-index: 999997;

        background:
            radial-gradient(
                ellipse at center,
                transparent 50%,
                rgba(0,0,0,.45) 100%
            );

        box-shadow:
            inset 0 0 100px rgba(0,0,0,.7);
    }

    /* =====================================================
       HEADER
       ===================================================== */

    .AppHeader {
        background:
            rgba(1,5,3,.94) !important;

        backdrop-filter:
            blur(14px);

        border-bottom:
            1px solid var(--line) !important;

        box-shadow:
            0 0 20px rgba(0,255,102,.08),
            inset 0 -1px rgba(0,255,102,.05);
    }

    /* =====================================================
       LINKS
       ===================================================== */

    a {
        color:
            var(--green) !important;

        transition:
            color .15s,
            text-shadow .15s;
    }

    a:hover {
        color:
            #ffffff !important;

        text-decoration:
            none !important;

        text-shadow:
            0 0 5px var(--green),
            0 0 12px var(--green),
            0 0 25px rgba(0,255,102,.5);
    }

    /* =====================================================
       PANELS
       ===================================================== */

    .Box {
        background:
            linear-gradient(
                135deg,
                rgba(5,17,11,.96),
                rgba(1,7,4,.96)
            ) !important;

        border:
            1px solid var(--line) !important;

        border-radius:
            3px !important;

        box-shadow:
            0 0 20px rgba(0,255,102,.025),
            inset 0 0 30px rgba(0,255,102,.015);

        transition:
            border .2s,
            box-shadow .2s,
            transform .2s;
    }

    .Box:hover {
        border-color:
            rgba(0,255,102,.45) !important;

        box-shadow:
            0 0 20px rgba(0,255,102,.12),
            inset 0 0 25px rgba(0,255,102,.025);

        transform:
            translateY(-1px);
    }

    /* =====================================================
       BUTTONS
       ===================================================== */

    .Button,
    .btn {
        background:
            #04100a !important;

        color:
