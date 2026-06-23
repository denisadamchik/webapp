# TypeScript Web Application (Tutorial Project)

This repository contains a standalone web application built as part of the hands-on tutorial in **Chapters 16 & 17** of the book **"Essential TypeScript"** by Adam Freeman (Manning Publications).

The project demonstrates how to configure, build, and deploy a complete TypeScript application without heavy frameworks, integrating a static frontend, a data layer using Axios, and a local simulated backend.

## 🚀 Key Features Covered

- **TypeScript Compiler Orchestration**: Advanced configuration utilizing `"moduleResolution": "bundler"` for modern dependency management.
- **Webpack Bundling**: Integrating Webpack to bundle TypeScript, styles, and assets into production-ready assets (`/dist`).
- **Unified Server Setup**: Utilizing an Express and `json-server` architecture (`server.js`) to host both the client-side frontend and a mock REST API on a single unified port.
- **Asynchronous Data Sources**: Leveraging Axios to query backend services dynamically.

---

## 🛠️ Prerequisites

Before running the project, ensure you have the following installed:

- [Node.js](https://nodejs.org) (v18.14.0 or later recommended to match the target environment)
- [Docker Engine](https://docker.com) (Optional, if you wish to containerize the app)

---

## 💻 Getting Started

### 1. Clone & Install Dependencies

Clone the repository and install the required NPM packages:

```bash
git clone https://github.com/denisadamchik/webapp.git
cd webapp
npm install
```

### 2. Build the Application

Compile the TypeScript code and let Webpack bundle your application assets into the `/dist` directory:

```bash
npm run build
```

### 3. Run the Unified Local Server

Launch the server environment. This script runs Express to serve the static frontend alongside `json-server` to power the REST API (`data.json`):

```bash
node server.js
```

_The server will fallback to port `4000` unless explicitly provided as a CLI argument._

---

## 🐳 Running with Docker

If you want to containerize the build and isolate the environment, use the included Dockerfile configuration.

### Build the Docker Image

```bash
docker build . -t webapp
```

### Run the Container

Map the required server port (`4000`) and start the application container:

```bash
docker run -p 4000:4000 webapp
```

Once started, the application will be accessible at `http://localhost:4000`.

---

## 📚 Reference material

- **Book**: _Essential TypeScript_ by Adam Freeman (Manning Publications)
- **Target Configurations**: `target: ES2022`, JSX factory custom handling, and strict module resolution.
