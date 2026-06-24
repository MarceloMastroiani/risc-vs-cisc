# RISC vs CISC — Presentación Interactiva

Presentación educativa tipo scrollytelling sobre arquitecturas de procesadores RISC y CISC, desarrollada con React, TypeScript y GSAP. Construida para el coloquio de Arquitectura de Computadoras en la UNER.

🔗 **[Ver demo en vivo](https://marcelomastroiani.github.io/arquitectura-coloquio)**

---

## ¿Qué es?

Una presentación web interactiva que explica las diferencias entre las arquitecturas RISC (*Reduced Instruction Set Computer*) y CISC (*Complex Instruction Set Computer*), con animaciones al hacer scroll, componentes interactivos y efectos visuales. Pensada para ser presentada en clase, no para leerse como un documento estático.

---

## Stack

| Tecnología | Uso |
|---|---|
| React 19 | UI y componentes |
| TypeScript | Tipado estático |
| Vite | Bundler y dev server |
| Tailwind CSS v4 | Estilos |
| GSAP | Animaciones de scroll y transiciones |
| Framer Motion | Animaciones declarativas de componentes |
| @dnd-kit | Interactividad drag & drop |
| canvas-confetti | Efectos visuales |
| lucide-react | Íconos |
| gh-pages | Deploy a GitHub Pages |

---

## Estructura del proyecto

```
src/
├── main.tsx              # Entry point
├── App.tsx               # Componente raíz, orquesta las secciones
├── components/           # Componentes reutilizables (tarjetas, comparadores, etc.)
├── sections/             # Cada sección/slide de la presentación
└── assets/               # Recursos estáticos
```

La presentación está dividida en secciones independientes que se van revelando al hacer scroll. Cada sección es un componente React que encapsula su propia lógica de animación.

---

## Animaciones

Se usan dos librerías de animación con roles distintos:

**GSAP + ScrollTrigger** maneja las animaciones atadas al scroll: elementos que entran al viewport, efectos de paralaje, timelines que avanzan a medida que el usuario baja por la página.

**Framer Motion** se usa para animaciones declarativas dentro de los componentes: transiciones entre estados, hover effects, montaje/desmontaje de elementos con `AnimatePresence`.

---

## Interactividad

Más allá de las animaciones, la presentación incluye componentes interactivos para que el contenido no sea solo pasivo:

**Drag & Drop** implementado con `@dnd-kit` — permite arrastrar elementos para comparar o clasificar características de cada arquitectura.

**Comparadores visuales** que muestran side-by-side las diferencias entre RISC y CISC en aspectos como tamaño de instrucciones, ciclos de clock, complejidad del compilador y uso de registros.

**Confetti** con `canvas-confetti` para feedback visual en interacciones correctas.

---

## Deploy

El proyecto se despliega automáticamente a GitHub Pages con:

```bash
pnpm run deploy
```

Esto ejecuta `tsc -b && vite build` y luego sube el contenido de `/dist` a la rama `gh-pages` usando el paquete `gh-pages`.

---

## Instalación local

```bash
# Clonar
git clone https://github.com/MarceloMastroiani/arquitectura-coloquio.git
cd arquitectura-coloquio

# Instalar dependencias
pnpm install

# Dev server
pnpm dev

# Build de producción
pnpm build

# Preview del build
pnpm preview
```

---

## Contexto académico

Desarrollado para el coloquio de la materia **Arquitectura de Computadoras** en la **Universidad Nacional de Entre Ríos (UNER)**. El objetivo era presentar los conceptos de forma visualmente atractiva e interactiva en lugar de una presentación de diapositivas tradicional.
