# Primer on HTML Rendering Approaches and Meta-Frameworks

This article provides a concise overview of different HTML rendering methods and meta-frameworks (such as Next.js, Remix, Nuxt or SvelteKit) for modern web development. We'll explore static file servers, multi-page applications (MPAs), single-page applications (SPAs), and transitional applications. Understanding these approaches helps developers choose the right approach for creating web-based user experience that fit the business demands at hand. Each technique has unique advantages and challenges regarding the user and the developer experience. This article aims to inform you about the nuances of each approach, so you can choose the right tool for building your next web application!

## Static File Servers

As a starting point, the most basic approach uses static HTML files that reside on a server. The files are typically located in folders in a hierarchical file system structure and correspond to URL routes. The server transmits the contents of the requested HTML file when a client requests it.

## Multi-Page Applications (Traditional Server-Side Rendering)

In traditional server-side rendering, as seen in technologies such as PHP or Ruby, the server takes an HTML template and sends it to the client. This typically results in a fast initial load time. The server can optionally inject data from a database into the template to dynamically render HTML. Content is generated in response to a client request and involves server-side processing. This allows for data-driven web applications that can be tailored to the logged-in user. The downside is that a subsequent navigation leads to a full page load, although oftentimes only parts of the web page change. The experience can be enhanced by including JS to request additional data without a full page reload, but JS resources must be requested and evaluated on each page load. Nowadays, applications with this technique are referred to as **multi-page applications (MPAs)**[^1] [^2].

## Single-page Applications (Client-Side Rendering)

**Single-page applications (SPA)** are usually built with frameworks like React, Vue, Angular, or Svelte. For an SPA the server transmits a mostly empty HTML shell with a single root element. Nothing of interest can be seen until the client loads JS to mount the root element by dynamically rendering components as HTML elements inside of the root element. This slow initial page load time is a typical downside of a SPA[^3]. This mounting process and eventual UI updates happen on the client, thus this approach is called **client-side rendering (CSR)**. Besides the relatively heavy payload of the SPA framework, another downside is the reduced SEO performance because web crawlers don't necessarily execute JS. On the other hand, SPAs can provide fast, interactive experiences because subsequent navigations are handled and rendered client-side, which doesn't lead to full page re-loads. Nate Moore[^4] – co-creator and core maintainer of the MPA framework Astro – goes as far as admitting that \"\[c\]lient-side routing is currently the only way to achieve UI persistence across navigations\". So, CSR can accomplish user experiences like \"tween\[ing\] a numeric value in a progress indicator\" that wouldn't be possible otherwise[^1].

## Transitional Applications

Transitional applications combine the benefits of SPAs and MPAs. The term was coined by Rich Harris[^5], the creator of Svelte. They are built with an SPA framework which is typically extended by an accompanying meta-framework like Next or Remix for React, Nuxt for Vue, or SvelteKit for Svelte. Transitional applications achieve this by using both server-side and client-side rendering. Such an application can be considered \"isomorphic\" or \"universal\" because JavaScript and framework code run both on the server and the client[^6].

When a user first opens a page, the application renders components into HTML strings server-side with JS, i.e. using the `renderToString()` function[^7] [^8]. This is referred to as **server-side rendering (SSR)**. The rendered HTML is then sent to the client similar to an MPA. This results in a fast initial load time, though the page has no JS interactivity, yet. Once JS loads, a process called hydration enables SPA-like interactivity features by registering event handlers and letting a client-site router take over navigation. So, subsequent navigations are rendered client-side and thus fast.

If the client did not load JS – e.g. due to poor network connectivity on the go – navigation is still possible because in that case the next page will be rendered server-side. Therefore, the mentioned client-side features can be seen as progressive enhancement. However, Harris[^5] acknowledges that adding hydration and client-side rendering to an otherwise server-side rendered page leads to \"serving data and component code that isn't strictly necessary\" but highlights that \"it's a very active area of research and development\".

Another aspect that transitional applications facilitate is **prerendering**. The SvelteKit documentation states it as follows[^9]:

> "Prerendering means computing the contents of a page at build time and saving the HTML for display. This approach has the same benefits as traditional server-rendered pages, but avoids recomputing the page for each visitor and so scales nearly for free as the number of visitors increases. The tradeoff is that the build process is more expensive and prerendered content can only be updated by building and deploying a new version of the application.\"

However, the content can only be prerendered if the required page content for server-side rendering is the same for each user[^6]. But prerendered pages are also not limited to static content[^9]. They can be personalized by fetching data client-side which comes with the downsides of not doing SSR for that content. The term **static site generation (SSG)** is sometimes interchangeably used instead of prerendering but more precisely describes websites where every page is prerendered. Static site generators are specialized tools, that focus only on this use case and are therefore optimized to efficiently generate large numbers of pages.

[^1]: Harris, Rich (2023). [Rich Harris on Frameworks, the Web, and the Edge [Video]](https://www.youtube.com/watch?v=uXCipjbcQfM). Vercel [YouTube Channel] 🌶🌶🌶🌶🌶. [MPA's at 9:32](https://youtu.be/uXCipjbcQfM?t=572). [UI persistence at 11:14](https://youtu.be/uXCipjbcQfM?t=673)
[^2]: Dodds, Kent C. (2023). [The Web’s Next Transition](https://www.epicweb.dev/the-webs-next-transition).
[^3]: Vue Maintainers (2023). [Performance | Vue.Js](https://vuejs.org/guide/best-practices/performance.html#page-load-optimizations).
[^4]: [Moore, Nate. Client-Side Routing - Issue - #532 - Withastro/Roadmap (2023)](https://github.com/withastro/roadmap/issues/532).
[^5]: Harris, Rich (2021). [Have Single-Page Apps Ruined the Web? | Transitional Apps with Rich Harris, NYTimes [Video]](https://www.youtube.com/watch?v=860d8usGC0o). Jamstack TV [YouTube Channel]. [Hydration and client-side rendering are overhead 14:55](https://youtu.be/860d8usGC0o?t=892)
[^6]: Vue Maintainers (2023). [Server-Side Rendering (SSR) | Vue.Js](https://vuejs.org/guide/scaling-up/ssr.html#what-is-ssr).
[^7]: React Maintainers. [renderToString - React (2023)](https://react.dev/reference/react-dom/server/renderToString).
[^8]: Vue maintainers. [Server-Side Rendering API | Vue.Js (2023)](https://vuejs.org/api/ssr.html#rendertostring).
[^9]: [Glossary - Docs - SvelteKit](https://kit.svelte.dev/docs/glossary)
