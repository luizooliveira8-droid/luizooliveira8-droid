@-moz-document domain("github.com") {

    /* =========================
       HACKER MODE
       ========================= */

    :root {
        --bg: #000000;
        --bg2: #050a05;
        --green: #00ff41;
        --green2: #00cc33;
        --dark-green: #003b12;
        --border: #064d1a;
        --text: #b7ffbf;
    }

    /* Fundo */
    body,
    .application-main,
    main {
        background: var(--bg) !important;
        color: var(--text) !important;
        font-family: "Courier New", monospace !important;
    }

    /* Header */
    header,
    .AppHeader {
        background: #000 !important;
        border-bottom: 1px solid var(--border) !important;
        box-shadow: 0 0 15px #00ff4122 !important;
    }

    /* Texto */
    body,
    p,
    span,
    div {
        font-family: "Courier New", monospace;
    }

    /* Links */
    a {
        color: var(--green) !important;
        text-shadow: 0 0 5px #00ff4166;
    }

    a:hover {
        color: #7dff91 !important;
        text-shadow: 0 0 12px var(--green);
    }

    /* Cards */
    .Box,
    .BorderGrid-cell {
        background: var(--bg2) !important;
        border-color: var(--border) !important;
        border-radius: 3px !important;
        box-shadow: 0 0 10px #00ff4110 !important;
    }

    /* Botões */
    .btn {
        background: #001a08 !important;
        color: var(--green) !important;
        border: 1px solid var(--green2) !important;
        border-radius: 2px !important;
        font-family: "Courier New", monospace !important;
    }

    .btn:hover {
        background: #003b12 !important;
        color: #fff !important;
        box-shadow: 0 0 15px #00ff4166 !important;
    }

    /* Inputs */
    input,
    textarea,
    select {
        background: #000 !important;
        color: var(--green) !important;
        border: 1px solid var(--border) !important;
        border-radius: 2px !important;
        font-family: "Courier New", monospace !important;
    }

    input:focus,
    textarea:focus {
        border-color: var(--green) !important;
        outline: none !important;
        box-shadow: 0 0 10px #00ff4144 !important;
    }

    /* Código */
    pre,
    code,
    .highlight {
        background: #020602 !important;
        color: var(--green) !important;
        border-color: var(--border) !important;
        font-family: "Courier New", monospace !important;
    }

    /* Títulos */
    h1,
    h2,
    h3,
    h4 {
        color: var(--green) !important;
        font-family: "Courier New", monospace !important;
        text-shadow: 0 0 8px #00ff4155;
    }

    /* Linha divisória */
    hr {
        border-color: var(--border) !important;
    }

    /* Scrollbar */
    ::-webkit-scrollbar {
        width: 8px;
        height: 8px;
    }

    ::-webkit-scrollbar-track {
        background: #000;
    }

    ::-webkit-scrollbar-thumb {
        background: #005c19;
        border-radius: 0;
    }

    ::-webkit-scrollbar-thumb:hover {
        background: var(--green);
        box-shadow: 0 0 10px var(--green);
    }

    /* Seleção de texto */
    ::selection {
        background: var(--green);
        color: #000;
    }

}
