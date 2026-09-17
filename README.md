# \# Laravel REST API + Vue Starter

# 

# Egyszerű, újrahasználható full-stack starter repository Laravel és Vue projektekhez.

# 

# A repository két egymástól független részből áll:

# 

# \- \*\*`backend\_laravel`\*\* — Laravel REST API + Scribe API dokumentáció

# \- \*\*`frontend\_vue`\*\* — Vue + Axios + Tailwind CSS

# 

# A backend és a frontend \*\*külön-külön is használható\*\*, nem szükséges őket együtt alkalmazni.

# 

# \---

# 

# \## Projektstruktúra

# 

# ```text

# .

# ├── backend\_laravel/

# │   ├── app/

# │   ├── bootstrap/

# │   ├── config/

# │   ├── database/

# │   ├── public/

# │   ├── resources/

# │   ├── routes/

# │   ├── storage/

# │   ├── tests/

# │   ├── artisan

# │   ├── composer.json

# │   └── ...

# │

# ├── frontend\_vue/

# │   ├── public/

# │   ├── src/

# │   ├── index.html

# │   ├── package.json

# │   ├── vite.config.ts

# │   └── ...

# │

# └── README.md

# ```

# 

# \---

# 

# \# Backend — Laravel REST API

# 

# A `backend\_laravel` egy Laravel alapú backend starter, amely REST API-k készítésére van előkészítve.

# 

# \### Tartalmazza

# 

# \- Laravel

# \- REST API routing

# \- Scribe API dokumentáció

# \- Laravel migrations

# \- Validation / Form Requests támogatás

# \- API Resources támogatás

# \- PHPUnit tesztelési környezet

# 

# \## Telepítés

# 

# ```bash

# cd backend\_laravel

# composer install

# ```

# 

# Hozd létre a saját `.env` fájlodat:

# 

# ```bash

# cp .env.example .env

# ```

# 

# Windows CMD esetén:

# 

# ```cmd

# copy .env.example .env

# ```

# 

# Generáld le az application key-t:

# 

# ```bash

# php artisan key:generate

# ```

# 

# Állítsd be az adatbázis-kapcsolatot a `.env` fájlban, majd:

# 

# ```bash

# php artisan migrate

# ```

# 

# \## Backend indítása

# 

# ```bash

# php artisan serve

# ```

# 

# Alapértelmezetten:

# 

# ```text

# http://127.0.0.1:8000

# ```

# 

# Az API route-ok:

# 

# ```text

# backend\_laravel/routes/api.php

# ```

# 

# \---

# 

# \## Scribe API dokumentáció

# 

# A projekt Scribe-bal dokumentálja a REST API végpontokat.

# 

# Dokumentáció generálása:

# 

# ```bash

# php artisan scribe:generate

# ```

# 

# A pontos dokumentációs URL a Scribe konfigurációjától függ.

# 

# A konfiguráció itt található:

# 

# ```text

# backend\_laravel/config/scribe.php

# ```

# 

# Új vagy módosított API endpointok után érdemes újragenerálni a dokumentációt:

# 

# ```bash

# php artisan scribe:generate

# ```

# 

# \---

# 

# \# Frontend — Vue

# 

# A `frontend\_vue` egy különálló Vue frontend starter.

# 

# \### Tartalmazza

# 

# \- Vue

# \- Vite

# \- Axios

# \- Tailwind CSS

# \- TypeScript támogatás

# 

# \## Telepítés

# 

# ```bash

# cd frontend\_vue

# npm install

# ```

# 

# \## Frontend indítása

# 

# ```bash

# npm run dev

# ```

# 

# A Vite alapértelmezetten általában:

# 

# ```text

# http://localhost:5173

# ```

# 

# címen indítja el a fejlesztői szervert.

# 

# \---

# 

# \## Axios

# 

# Az Axios használható a Laravel vagy bármilyen más REST API elérésére.

# 

# Példa:

# 

# ```ts

# import axios from 'axios'

# 

# const api = axios.create({

# &#x20;   baseURL: 'http://127.0.0.1:8000/api',

# &#x20;   headers: {

# &#x20;       Accept: 'application/json',

# &#x20;   },

# })

# 

# export default api

# ```

# 

# Éles projektnél az API URL-t célszerű environment változóként megadni.

# 

# Például:

# 

# ```env

# VITE\_API\_URL=http://127.0.0.1:8000/api

# ```

# 

# Használata:

# 

# ```ts

# const api = axios.create({

# &#x20;   baseURL: import.meta.env.VITE\_API\_URL,

# })

# ```

# 

# \---

# 

# \# Használat

# 

# A repository háromféleképpen használható.

# 

# \### Csak Laravel backend

# 

# Csak a következő mappára van szükség:

# 

# ```text

# backend\_laravel/

# ```

# 

# Használható például:

# 

# \- REST API backendként

# \- mobilalkalmazás backendjeként

# \- külön frontenddel

# \- külső API klienssel

# \- microservice-ként

# 

# \---

# 

# \### Csak Vue frontend

# 

# Csak a következő mappára van szükség:

# 

# ```text

# frontend\_vue/

# ```

# 

# A frontend bármilyen REST API-hoz csatlakoztatható Axios segítségével.

# 

# \---

# 

# \### Laravel + Vue

# 

# A két projekt együtt is használható:

# 

# ```text

# Vue

# &#x20; ↓

# Axios

# &#x20; ↓

# Laravel REST API

# &#x20; ↓

# Database

# ```

# 

# Fejlesztés közben például:

# 

# ```text

# Frontend:

# http://localhost:5173

# 

# Backend:

# http://127.0.0.1:8000

# 

# API:

# http://127.0.0.1:8000/api

# ```

# 

# \---

# 

# \# Production build

# 

# \## Vue

# 

# Production build készítése:

# 

# ```bash

# cd frontend\_vue

# npm run build

# ```

# 

# A build eredménye:

# 

# ```text

# frontend\_vue/dist/

# ```

# 

# \## Laravel

# 

# Production környezetben a Laravel optimalizálható:

# 

# ```bash

# php artisan optimize

# ```

# 

# Cache törlése:

# 

# ```bash

# php artisan optimize:clear

# ```

# 

# \---

# 

# \# Git

# 

# Az alábbi generált vagy érzékeny fájlokat nem szabad Git repositoryba commitolni.

# 

# Laravel:

# 

# ```text

# backend\_laravel/.env

# backend\_laravel/vendor/

# ```

# 

# Vue:

# 

# ```text

# frontend\_vue/.env

# frontend\_vue/node\_modules/

# frontend\_vue/dist/

# ```

# 

# A következő fájlokat viszont érdemes commitolni:

# 

# ```text

# backend\_laravel/.env.example

# backend\_laravel/composer.lock

# 

# frontend\_vue/package-lock.json

# ```

# 

# \---

# 

# \# Követelmények

# 

# \### Laravel backend

# 

# \- PHP

# \- Composer

# \- Laravel által támogatott adatbázis

# 

# \### Vue frontend

# 

# \- Node.js

# \- npm

# 

# \---

# 

# \# Quick Start

# 

# \## Backend

# 

# ```bash

# cd backend\_laravel

# composer install

# cp .env.example .env

# php artisan key:generate

# php artisan migrate

# php artisan serve

# ```

# 

# \## Frontend

# 

# ```bash

# cd frontend\_vue

# npm install

# npm run dev

# ```

# 

# \---

# 

# \## Tech Stack

# 

# \*\*Backend\*\*

# 

# ```text

# Laravel

# REST API

# Scribe

# Composer

# ```

# 

# \*\*Frontend\*\*

# 

# ```text

# Vue

# Vite

# Axios

# Tailwind CSS

# TypeScript

# ```

# 

# \---

# 

# \## Megjegyzés

# 

# A két projekt nincs szorosan összekötve egymással.

# 

# A `backend\_laravel` és a `frontend\_vue` önálló starterként is használható, ezért egy új projekt indításakor csak azt a részt kell megtartani, amelyre szükség van.

