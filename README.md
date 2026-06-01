# Fluid Shader Art

An interactive WebGL fluid shader overlay built with **Next.js** and **React.js**. The shader simulates a fluid dynamics effect (velocity, pressure, advection) rendered on top of a background image using a WebGL canvas.

---

## Demo

Move your mouse or tap the screen to interact with the oil fluid effect.

---

## Features

- Real-time fluid simulation using WebGL (Navier-Stokes based)
- Mouse & touch interaction support
- Auto-animated motion when idle
- Customizable color, resolution, and fluid parameters
- Built as a reusable React component

---

## Tech Stack

- [Next.js](https://nextjs.org/)
- [React.js](https://react.dev/)
- [Tailwind CSS](https://tailwindcss.com/)
- WebGL (vanilla, no extra libraries)

---

## Getting Started

### 1. Install dependencies

```bash
npm install
```

### 2. Run the dev server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## Usage

The `ShaderComponent` is a wrapper — place any content inside it:

```jsx
import ShaderComponent from "@/components/hero";

export default function Page() {
  return (
    <ShaderComponent>
      <h1>Your content here</h1>
    </ShaderComponent>
  );
}
```

---

## Customization

Edit the `params` object in `src/components/hero.jsx` to tweak the effect:

```js
const params = {
  SIM_RESOLUTION: 128,        // Simulation grid resolution
  DYE_RESOLUTION: 1024,       // Color/dye resolution
  DENSITY_DISSIPATION: 0.995, // How fast color fades
  VELOCITY_DISSIPATION: 0.9,  // How fast fluid slows down
  PRESSURE_ITERATIONS: 10,    // Pressure solver iterations
  SPLAT_RADIUS: 3 / window.innerHeight, // Size of fluid splat
  color: { r: 0.5, g: 0.5, b: 0.5 }   // RGB color of the fluid
};
```

To change the background image, drop your image into `src/assets/` and update the import in `hero.jsx`:

```js
import myImage from "@/assets/your-image.png";
```

---

## Project Structure

```
src/
├── app/
│   ├── page.js        # Entry page
│   ├── layout.js      # Root layout
│   └── globals.css    # Global styles
├── components/
│   └── hero.jsx       # ShaderComponent (WebGL fluid effect)
└── assets/
    └── your-image.png # Background image
```

---

## License

MIT
