# Laravel REST API + Vue Starter

Egyszerű, újrahasználható full-stack starter repository Laravel és Vue projektekhez.

A repository két egymástól független részből áll:

- **`backend_laravel`** — Laravel REST API + Scribe API dokumentáció
- **`frontend_vue`** — Vue + Axios + Tailwind CSS

A backend és a frontend **külön-külön is használható**, nem szükséges őket együtt alkalmazni.

---

## Projektstruktúra

```text
.
├── backend_laravel/
│   ├── app/
│   ├── bootstrap/
│   ├── config/
│   ├── database/
│   ├── public/
│   ├── resources/
│   ├── routes/
│   ├── storage/
│   ├── tests/
│   ├── artisan
│   ├── composer.json
│   └── ...
│
├── frontend_vue/
│   ├── public/
│   ├── src/
│   ├── index.html
│   ├── package.json
│   ├── vite.config.ts
│   └── ...
│
└── README.md
```

---

# Backend — Laravel REST API

A `backend_laravel` egy Laravel alapú backend starter, amely REST API-k készítésére van előkészítve.

### Tartalmazza

- Laravel
- REST API routing
- Scribe API dokumentáció
- Laravel migrations
- Validation / Form Requests támogatás
- API Resources támogatás
- PHPUnit tesztelési környezet

## Telepítés

```bash
cd backend_laravel
composer install
```

Hozd létre a saját `.env` fájlodat:

```bash
cp .env.example .env
```

Windows CMD esetén:

```cmd
copy .env.example .env
```

Generáld le az application key-t:

```bash
php artisan key:generate
```

Állítsd be az adatbázis-kapcsolatot a `.env` fájlban, majd:

```bash
php artisan migrate
```

## Backend indítása

```bash
php artisan serve
```

Alapértelmezetten:

```text
http://127.0.0.1:8000
```

Az API route-ok:

```text
backend_laravel/routes/api.php
```

---

## Scribe API dokumentáció

A projekt Scribe-bal dokumentálja a REST API végpontokat.

Dokumentáció generálása:

```bash
php artisan scribe:generate
```

A pontos dokumentációs URL a Scribe konfigurációjától függ.

A konfiguráció itt található:

```text
backend_laravel/config/scribe.php
```

Új vagy módosított API endpointok után érdemes újragenerálni a dokumentációt:

```bash
php artisan scribe:generate
```

---

# Frontend — Vue

A `frontend_vue` egy különálló Vue frontend starter.

### Tartalmazza

- Vue
- Vite
- Axios
- Tailwind CSS
- TypeScript támogatás

## Telepítés

```bash
cd frontend_vue
npm install
```

## Frontend indítása

```bash
npm run dev
```

A Vite alapértelmezetten általában:

```text
http://localhost:5173
```

címen indítja el a fejlesztői szervert.

---

## Axios

Az Axios használható a Laravel vagy bármilyen más REST API elérésére.

Példa:

```ts
import axios from 'axios'

const api = axios.create({
    baseURL: 'http://127.0.0.1:8000/api',
    headers: {
        Accept: 'application/json',
    },
})

export default api
```

Éles projektnél az API URL-t célszerű environment változóként megadni.

Például:

```env
VITE_API_URL=http://127.0.0.1:8000/api
```

Használata:

```ts
const api = axios.create({
    baseURL: import.meta.env.VITE_API_URL,
})
```

---

# Használat

A repository háromféleképpen használható.

### Csak Laravel backend

Csak a következő mappára van szükség:

```text
backend_laravel/
```

Használható például:

- REST API backendként
- mobilalkalmazás backendjeként
- külön frontenddel
- külső API klienssel
- microservice-ként

---

### Csak Vue frontend

Csak a következő mappára van szükség:

```text
frontend_vue/
```

A frontend bármilyen REST API-hoz csatlakoztatható Axios segítségével.

---

### Laravel + Vue

A két projekt együtt is használható:

```text
Vue
  ↓
Axios
  ↓
Laravel REST API
  ↓
Database
```

Fejlesztés közben például:

```text
Frontend:
http://localhost:5173

Backend:
http://127.0.0.1:8000

API:
http://127.0.0.1:8000/api
```

---

# Production build

## Vue

Production build készítése:

```bash
cd frontend_vue
npm run build
```

A build eredménye:

```text
frontend_vue/dist/
```

## Laravel

Production környezetben a Laravel optimalizálható:

```bash
php artisan optimize
```

Cache törlése:

```bash
php artisan optimize:clear
```

---

# Git

Az alábbi generált vagy érzékeny fájlokat nem szabad Git repositoryba commitolni.

Laravel:

```text
backend_laravel/.env
backend_laravel/vendor/
```

Vue:

```text
frontend_vue/.env
frontend_vue/node_modules/
frontend_vue/dist/
```

A következő fájlokat viszont érdemes commitolni:

```text
backend_laravel/.env.example
backend_laravel/composer.lock

frontend_vue/package-lock.json
```

---

# Követelmények

### Laravel backend

- PHP
- Composer
- Laravel által támogatott adatbázis

### Vue frontend

- Node.js
- npm

---

# Quick Start

## Backend

```bash
cd backend_laravel
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate
php artisan serve
```

## Frontend

```bash
cd frontend_vue
npm install
npm run dev
```

---

## Tech Stack

**Backend**

```text
Laravel
REST API
Scribe
Composer
```

**Frontend**

```text
Vue
Vite
Axios
Tailwind CSS
TypeScript
```

---

## Megjegyzés

A két projekt nincs szorosan összekötve egymással.

A `backend_laravel` és a `frontend_vue` önálló starterként is használható, ezért egy új projekt indításakor csak azt a részt kell megtartani, amelyre szükség van.
