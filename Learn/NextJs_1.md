## Top-level files
### NextJS is a framework to build a full-stack application with features such as server-side rendering using the React framework.

**Static sites: In this, HTML files are created at build time and copied this HTML files to CDN or Web server and accessible as static HTML files.**

**incremental static regeneration (ISR) In this, All the static HTML pages are generated at build time, any new page that is created or updated is generated at runtime, not the build time. Incremental means any new pages that were created updated or deleted. It does not generate all pages at runtime.**
- **In the SSR technique, the Server works as the opposite of single-page applications When a request is sent from a client to a server, the Server generates HTML sends HTML code to the client, and displays it to the user.**

## Generally eta Hoy But Advatnge of Next Js are : 
`- Server-side rendering and Single Page Application development` <br>
`- Static Site Generator`<br>
`- Code splitting`<br>
`- SEO`<br>
`- Build optimizations`<br>
`- Progress app features such as offline, prerender`<br>
`- Supports pre-generate HTML in the server as well as in-browser at build/run time`<br>
`- It is faster in development and development loading is good`<br>
`- Image Optimization`<br>
`- Page Routing`<br>
`- Better User experience`<br>
`- Hot Reloading`<br>

## NextJS disadvantages
`- It is overkill for simple applications` <br>
`- Build time is more`<br>
`  - Limited plugins`<br>
`  - State Management is not provided as part of the framework`<br>

- **These can be used in eCommerce sites as new products are added or existing products are updated with prices daily.**
**Top-level files are used to configure your application, manage dependencies, run middleware, integrate monitoring tools, and define environment variables.**


### Example :

```
 config.json 
 package.json
 .env
 middleware.ts
 .env.local
 production
 deployment
```

## Routing Files

```angular2html
layout
page
loading
not-found
error
route
global-error
template
default
```
## Nested Routes
```
folder -------- Route segment
folder/folder ------- Nested route segment
```
## Dynamic Routes
```angular2html
[folder] ---- Dynamic route segment
[...folder] ---- Catch-all route segment
[[...folder]] --- Optional catch-all rute segment
```
## Groups and Private folders

## SEO 
```angular2html
sitemap .xlm
sitemap .js .ts
rebots .txt
rebots .js .ts
```
## Store project files outside of app

**This strategy stores all application code in shared folders in the root of your project and keeps the app directory purely for routing purposes.**
 
## We can store project file outside inside the app folder

**Next.js uses file-system based routing, meaning you can use folders and files to define routes. This page will guide you through how to create layouts and pages, and link between them.**
<br> 
- **A page is UI that is rendered on a specific route.**
- **A layout is UI that is shared between multiple pages. On navigation, layouts preserve state, remain interactive, and do not rerender.**

## You can define a layout by default exporting a React component from a layout file. The component should accept a children prop which can be a page or another layout.

## Linking between pages
**You can use the <Link> component to navigate between routes. ``<Link>`` is a built-in Next.js 
component that extends the HTML ``<a>`` tag to provide prefetching and 
client-side navigation.**

## How to optimize images

**The Next.js ``<Image>`` component extends the HTML ``<img>`` element to provide:**

- **Size optimization: Automatically serving correctly sized images for each device, using modern image formats like WebP.**
- **Visual stability: Preventing layout shift automatically when images are loading.**
- **Faster page loads: Only loading images when they enter the viewport using native browser lazy loading, with optional blur-up placeholders.**
- **Asset flexibility: Resizing images on-demand, even images stored on remote servers.**

**To start using ``<Image>``, import it from next/image and render it within your component.**

```tsx
import Image from 'next/image'
 
export default function Page() {
  return <Image src="" alt="" />
}
```

**Since Next.js does not have access to remote files during the build process, you'll need to provide the width, height and optional blurDataURL props manually. The width and height are used to infer the correct aspect ratio of image and avoid layout shift from the image loading in.**

## Google Fonts
**You can automatically self-host any Google Font. Fonts are included stored as static assets and served from the same domain as your deployment, meaning no requests are sent to Google by the browser when the user visits your site.**

```tsx
import { Geist } from 'next/font/google'
 
const geist = Geist({
  subsets: ['latin'],
})
 
export default function RootLayout({
  children,
}: {
  children: React.ReactNode
}) {
  return (
    <html lang="en" className={geist.className}>
      <body>{children}</body>
    </html>
  )
}
```
```tsx
import { Roboto } from 'next/font/google'
 
const roboto = Roboto({
  weight: '400',
  subsets: ['latin'],
})
 
export default function RootLayout({
  children,
}: {
  children: React.ReactNode
}) {
  return (
    <html lang="en" className={roboto.className}>
      <body>{children}</body>
    </html>
  )
}
```

## How to use CSS
`- CSS Modules : same as class base design`
```css
.blog {
  padding: 24px;
}
```
```tsx
import styles from './blog.module.css'
 
export default function Page() {
  return <main className={styles.blog}></main>
}
```
`- Global CSS : same as class base`
`- External CSS : like Bootstrap`

## How to use Partial Prerendering

**Partial Prerendering (PPR) is a rendering strategy that allows you to combine static and dynamic content in the same route. This improves the initial page performance while still supporting personalized, dynamic data.**

<img src="https://nextjs.org/_next/image?url=https%3A%2F%2Fh8DxKfmAPhn8O0p3.public.blob.vercel-storage.com%2Flearn%2Flight%2Fthinking-in-ppr.png&w=1920&q=75">

## When a user visits a route:

1. The server sends a shell containing the static content, ensuring a fast initial load.
2. The shell leaves holes for the dynamic content that will load in asynchronously.
3. The dynamic holes are streamed in parallel, reducing the overall load time of the page.








