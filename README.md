# How to Build Unique, Beautiful Websites with Tailwind CSS

## Getting Started with Tailwind

```bash
pnpm init
pnpm install tailwindcss -D
```

The next step is to create a <code>styles.css</code>, where we include the framework styles using the <code>@tailwind</code> directive:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

```bash
pnpm tailwind init
npx tailwind build styles.css -o output.css
touch index.html
```

*<code>npx tailwind build styles.css -o output.css</code> should be run every time you make changes to your styles.*

Finally, we link the generated <code>output.css</code> file and <code>Font Awesome</code> to our <code>index.html</code> file:

```html
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.9.0/css/all.min.css">
    <link rel="stylesheet" type="text/css" href="output.css">
```

## Building a One-Page Website Template

### Header (Logo, Navigation)

### Services

### Projects

Create and share the custom <code>section</code> component:

```css
/* styles.css */
...
@tailwind components;

.section {
    @apply w-full p-6;
}

.section-title {
    @apply w-48 mx-auto pt-6 border-b-2 border-orange-500 text-center text-2xl text-blue-700;
}

.section-subtitle {
    @apply p-2 text-center text-lg text-gray-700;
}
...
```

Create our own utilities:

```css
/* styles.css */
...
@tailwind utilities;

.-skewx-20 {
    transform: skewX(-20deg);
}
...
```

Custom the default Tailwind theme:

```js
// tailwind.config.js
/** @type {import('tailwindcss').Config} */
  ...
  theme: {
    extend: {
      borderRadius: {
        'xl': '1rem',
        '2xl': '2rem',
        '3xl': '3rem',
      }
    },
  },
  ...
```

There's one more thing we want to do which Tailwind doesn't offer by default. We want the card to rise up a bit on hover. So we need to add a subtle nagitive margin on hover. But to make it work we need to enable the <code>hover</code> variant to the <code>margin</code> utility:

```js
// tailwind.config.js
/** @type {import('tailwindcss').Config} */
  ...
  variants: {
    margin: ['responsive', 'hover'],
  },
  ...
```

The important thing here is that we must always provide the complete list of variants we want to enable, not only the new ones.

### Team

### Footer (About, Contacts)

See the code in <code>index.html</code> for details.
