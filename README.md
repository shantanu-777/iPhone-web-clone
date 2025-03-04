# iPhone 15 Website Clone

## Table of Contents

1. [Introduction](#introduction)
2. [Tech Stack](#tech-stack)
3. [Features](#features)
4. [Quick Start](#quick-start)
5. [Code Snippets](#code-snippets)

## Introduction

This project is a clone of Apple's iPhone 15 Pro website, built using React.js and TailwindCSS. It incorporates Three.js and GSAP for smooth animations and dynamic 3D model rendering of the iPhone 15 Pro in various colors.

## Tech Stack

- React.js
- Three.js
- React Three Fiber
- React Three Drei
- GSAP (Greensock)
- Vite
- Tailwind CSS

## Features

- **Smooth Animations**: Uses GSAP for seamless transitions and effects.
- **3D Model Rendering**: Interactive iPhone 15 Pro models with different color and size options.
- **Custom Video Carousel**: Engaging user experience powered by GSAP.
- **Responsive Design**: Optimized for all screen sizes.

## Quick Start

Follow these steps to set up the project locally.

### Prerequisites

Ensure you have the following installed:

- [Git](https://git-scm.com/)
- [Node.js](https://nodejs.org/en)
- [npm](https://www.npmjs.com/)

### Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/JavaScript-Mastery-Pro/iphone-doc.git
cd iphone-doc
npm install
```

Run the project:

```bash
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

## Code Snippets

### Tailwind Configuration

```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
  theme: {
    extend: {
      colors: {
        blue: "#2997FF",
        gray: {
          DEFAULT: "#86868b",
          100: "#94928d",
          200: "#afafaf",
          300: "#42424570",
        },
        zinc: "#101010",
      },
    },
  },
  plugins: [],
};
```

### Lights Component

```javascript
import { Environment, Lightformer } from "@react-three/drei";

const Lights = () => {
  return (
    <group name="lights">
      <Environment resolution={256}>
        <group>
          <Lightformer form="rect" intensity={10} position={[-1, 0, -10]} scale={10} color={"#495057"} />
          <Lightformer form="rect" intensity={10} position={[-10, 2, 1]} scale={10} rotation-y={Math.PI / 2} />
          <Lightformer form="rect" intensity={10} position={[10, 0, 1]} scale={10} rotation-y={Math.PI / 2} />
        </group>
      </Environment>
      <spotLight position={[-2, 10, 5]} angle={0.15} penumbra={1} decay={0} intensity={Math.PI * 0.2} color={"#f8f9fa"} />
      <spotLight position={[0, -25, 10]} angle={0.15} penumbra={1} decay={0} intensity={Math.PI * 0.2} color={"#f8f9fa"} />
      <spotLight position={[0, 15, 5]} angle={0.15} penumbra={1} decay={0.1} intensity={Math.PI * 3} />
    </group>
  );
};

export default Lights;
```

