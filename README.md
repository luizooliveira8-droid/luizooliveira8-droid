// ==UserScript==
// @name         GitHub Custom Theme
// @namespace    github-custom-theme
// @version      1.0
// @description  Personaliza a aparência do GitHub
// @match        https://github.com/*
// @grant        GM_addStyle
// ==/UserScript==

(function () {
    'use strict';

    GM_addStyle(`
        /* Fundo geral */
        body {
            background: #0b0f14 !important;
            color: #e6edf3 !important;
        }

        /* Cabeçalho */
        .AppHeader {
            background: #0d1117 !important;
            border-bottom: 1px solid #30363d !important;
        }

        /* Links */
        a {
            color: #58a6ff !important;
        }

        a:hover {
            color: #79c0ff !important;
            text-decoration: none !important;
        }

        /* Cards e caixas */
        .Box,
        .BorderGrid-row,
        .repository-content,
        .markdown-body {
            background: #111820 !important;
            border-color: #30363d !important;
        }

        /* Botões */
        .Button,
        .btn {
            background: #21262d !important;
            color: #e6edf3 !important;
            border-color: #30363d !important;
            border-radius: 8px !important;
        }

        .Button:hover,
        .btn:hover {
            background: #30363d !important;
        }

        /* Campo de pesquisa */
        input,
        textarea {
            background: #0d1117 !important;
            color: #e6edf3 !important;
            border-color: #30363d !important;
            border-radius: 8px !important;
        }

        /* Código */
        pre,
        code {
            background: #090c10 !important;
            border-radius: 8px !important;
        }

        /* Barra lateral */
        .Layout-sidebar {
            background: #0d1117 !important;
        }

        /* Títulos */
        h1, h2, h3, h4 {
            color: #f0f6fc !important;
        }

        /* Avatar */
        img.avatar {
            border-radius: 50% !important;
            box-shadow: 0 0 0 2px #58a6ff;
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 10px;
        }

        ::-webkit-scrollbar-track {
            background: #0b0f14;
        }

        ::-webkit-scrollbar-thumb {
            background: #30363d;
            border-radius: 10px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: #484f58;
        }
    `);
})();
