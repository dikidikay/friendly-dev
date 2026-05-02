# The Friendly Dev 🧑‍💻

A full-stack, server-side rendered portfolio website for a web developer to showcase projects, share blog posts, and let visitors get in touch. Built with **React Router v7 in framework mode** while following the [Modern React From The Beginning](https://www.udemy.com/course/modern-react-from-the-beginning) course on Udemy.

## 🌐 Live Site

> [Live Site](https://dikidikay-friendly-dev.netlify.app)


## 🔗 Related Repositories

- **Backend (Strapi CMS):** [friendly-dev-backend](https://github.com/dikidikay/friendly-dev-backend)

---

## 📌 About the Project

The Friendly Dev is a personal portfolio web app with three core sections:

- **Projects** – Browse and filter a developer's portfolio projects, each with a dedicated detail page.
- **Blog** – Read developer-written posts with search and pagination support.
- **Contact** – Reach out via a contact form powered by Formspree.

---

## 🚀 What I Learned

This project served as a deep dive into modern full-stack React development. Here's what was covered:

### ⚛️ React Router v7 — Framework Mode
- Used React Router in **framework mode** (not library mode), which enables file-based routing conventions and server-side features.
- Defined routes declaratively in `routes.ts` using `route()`, `index()`, and `layout()` helpers.
- Used **layout routes** to share UI shells (e.g. Navbar) across multiple pages without re-rendering them.
- Implemented **loaders** to fetch data server-side before the page renders — keeping the UI clean and avoiding loading spinners.
- Explored **actions** for handling form submissions server-side (But in the end used Formspree).
- Configured SSR (`ssr: true`) in `react-router.config.ts` to ensure pages are rendered on the server.

### 🗄️ Strapi — Headless CMS
- Used **Strapi** as the backend content management system to handle projects and blog posts.
- Modeled content types in Strapi (Projects and Posts) with structured fields and relationships.
- Consumed Strapi's REST API from the React Router loaders using `populate` and `filters` query parameters.
- Integrated **Cloudinary** with Strapi so that image uploads are stored and served via Cloudinary's CDN instead of the local filesystem.

### 🐘 Neon — Serverless Postgres
- Connected Strapi to a **Neon** serverless PostgreSQL database to persist CMS content reliably in the cloud.

### 📬 Formspree — Contact Form
- Hooked up the contact form to **Formspree** so form submissions are forwarded to an email inbox without needing a custom backend endpoint.

### Deployment
- Deployed the **Strapi backend** to **Railway**.
- Deployed this **frontend** to **Netlify**.

### 🏗️ TypeScript & Type Safety
- Typed Strapi API responses with custom interfaces (`StrapiProject`, `StrapiPost`, `StrapiResponse<T>`), then mapped them to clean internal types (`Project`, `Post`) in each loader — keeping component code decoupled from the raw API shape.

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend Framework | React 19 + React Router v7 (Framework Mode) |
| Language | TypeScript |
| Styling | Tailwind CSS v4 + `@tailwindcss/typography` |
| Animation | Framer Motion |
| Icons | React Icons |
| Markdown Rendering | react-markdown |
| CMS | Strapi |
| Database | Neon (Serverless Postgres) |
| Image Storage | Cloudinary (via Strapi plugin) |
| Contact Form | Formspree |
| Build Tool | Vite |
| Backend Hosting | Railway |
| Frontend Hosting | Netlify |

---

## 🏁 Getting Started

### Prerequisites

- Node.js ≥ 20
- A running Strapi instance

### Environment Variables

Create a `.env` file in the project root:

```env
VITE_API_URL=https://your-strapi-api-url/api
VITE_STRAPI_URL=https://your-strapi-api-url
```

### Install & Run

```bash
npm install
npm run dev
```

### Build for Production

```bash
npm run build
npm run start
```

