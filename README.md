# Home Security Frontend (homesec)

A modern, secure, and responsive web app for home security monitoring, built with **Vite**, **React**, **TypeScript**, and **Tailwind CSS**.

---

## Features
- **Authentication:** Secure login/logout with device ID, email, and password
- **Dashboard:** Real-time device status, communication history, and security alerts
- **Profile Management:** Update email, password, phone, and notification preferences
- **Live Alerts:** Real-time security events via Server-Sent Events (SSE)
- **Responsive Design:** Mobile-first, accessible, and touch-friendly UI
- **API Integration:** Connects to a RESTful backend (see API endpoints below)

---

## Folder Structure
```
homesec/
  ├─ public/
  ├─ src/
  │   ├─ api/                # API utility functions
  │   ├─ assets/             # Static assets (e.g., icons)
  │   ├─ components/         # Reusable UI components
  │   ├─ hooks/              # Custom React hooks
  │   ├─ pages/              # Page components (Login, Dashboard)
  │   ├─ utils/              # Utility functions
  │   ├─ App.tsx             # Main app with routing
  │   ├─ main.tsx            # App entry point
  │   └─ index.css           # Tailwind base styles
  ├─ tailwind.config.cjs     # Tailwind CSS config
  ├─ tailwind.config.json    # Tailwind config (JSON, for tooling)
  ├─ postcss.config.cjs      # PostCSS config
  ├─ tsconfig.json           # TypeScript config
  ├─ vite.config.ts          # Vite config
  └─ README.md
```

---

## Setup & Development

1. **Install dependencies:**
   ```sh
   npm install
   ```

2. **Environment variables:**
   - Create a `.env` file in the root with:
     ```env
     VITE_API_URL=http://localhost:4000/api
     ```
     (Adjust the URL to match your backend.)

3. **Run the development server:**
   ```sh
   npm run dev
   ```
   The app will be available at [http://localhost:5173](http://localhost:5173)

4. **Build for production:**
   ```sh
   npm run build
   ```

---

## Scripts
- `npm run dev` — Start Vite dev server
- `npm run build` — Build for production
- `npm run preview` — Preview production build
- `npm run lint` — Run ESLint

---

## Backend API Endpoints (Expected)
- `POST   /api/auth/login` — Login
- `POST   /api/auth/logout` — Logout
- `GET    /api/users/me` — Get user profile
- `PATCH  /api/users/email` — Update email
- `PATCH  /api/users/password` — Update password
- `PATCH  /api/users/phone` — Update phone
- `GET    /api/devices/me` — Get device info
- `GET    /api/devices/status` — Get device status
- `GET    /api/alerts` — Get alerts
- `GET    /api/sse/alerts` — Real-time alerts (SSE)
- `POST   /api/password-resets/request` — Request password reset
- `POST   /api/password-resets/reset` — Reset password

---

## UI/UX Highlights
- Minimalist, card-based dashboard
- Pre-filled login form for demo/testing
- Profile update modal on first login
- Real-time updates for alerts and device status
- Accessible, mobile-friendly, and visually clear

---

## TypeScript React Setup Checklist
- [x] All component files use the `.tsx` extension
- [x] `tsconfig.json` includes: `"jsx": "react-jsx"`
- [x] `@types/react` and `@types/react-dom` are installed
- [x] React 18+ and react-router-dom 6+ are installed
- [x] Restart dev server and editor after config changes

---

## Common Errors & Solutions

### Property 'div' does not exist on type 'JSX.IntrinsicElements'
- **Cause:** TypeScript does not recognize JSX elements.
- **Fix:**
  1. Ensure your file extension is `.tsx`.
  2. In `tsconfig.json`, set: `"jsx": "react-jsx"` under `compilerOptions`.
  3. Install React types:
     ```sh
     npm install --save-dev @types/react @types/react-dom
     ```
  4. Restart your dev server and editor.

### 'Routes' not exported from 'react-router-dom'
- **Cause:** Using an old version of `react-router-dom`.
- **Fix:**
  ```sh
  npm install react-router-dom@latest
  ```

### '@typescript-eslint/no-unused-vars' for catch variables
- **Cause:** You have a catch block like `catch (err)` but do not use the `err` variable inside the block.
- **Fix:** Remove the variable if not used: `catch { ... }` or use the variable in your error handling.

---

## License
MIT (or your project license)
