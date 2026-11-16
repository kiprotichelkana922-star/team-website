# Team Name: Lab 2 Website

**Live site:** https://username.github.io/team-website/

## Team
KIPROTICH LANGAT ELKANA COM/3465/26 kiprotichelkana922-star
LAZARO KIPLIMO  SAMBURMO COM/3483/26 
## Who drove each part
- Part 0, 2, 4: LAZARO KIPLIMO SAMBURMO
- Part 1, 3: ELKANA KIPROTICH LANGAT
## Reflection

1. The menu toggle is a <button>, not a clickable <div>. Name two things you would lose with a <div>, and who would be affected.
With a <div>, you lose built-in keyboard focusability (reaching the element via the Tab key and activating it with Enter/Space) as well as semantic role announcements for assistive technologies. Keyboard-only users and blind or visually impaired users relying on screen readers would be affected, as they would be unable to navigate to or understand the purpose of the toggle.

2. What would break if you removed defer from the <script> tag in <head>? Explain why, in terms of how the browser parses HTML.
The browser parses HTML sequentially from top to bottom and immediately pauses to execute any script without defer. Because the <script> is in the <head>, it would run before the <body> elements are parsed into the DOM, causing querySelector or getElementById calls to return null and throw runtime errors when attaching event listeners.

3. renderProjects uses textContent rather than innerHTML. What could go wrong with innerHTML if project titles were typed in by visitors?
Using innerHTML parses user input as raw HTML markup rather than plain text, creating a Cross-Site Scripting (XSS) vulnerability. A malicious visitor could enter HTML tags or JavaScript event handlers (such as <img src=x onerror="...">) as a project title, causing arbitrary code to execute in the browsers of anyone viewing the page.

4. Your form checks its input with JavaScript. Why will the server still need to validate the same data once the form is connected to one?
Client-side JavaScript runs entirely on the user's device, meaning anyone can bypass it by disabling JavaScript, altering the page code in DevTools, or sending HTTP requests directly to the server endpoint. Server-side validation is mandatory to protect the backend database from malformed, incomplete, or malicious data.

5. Your theme choice follows you from Home to Contact, but not from a double-clicked file to Live Server. Explain this using the idea of an origin.
A browser origin is defined by the combination of protocol, host, and port, and localStorage is strictly isolated per origin for security. Double-clicking a file uses the file:// protocol while Live Server uses [http://127.0.0.1:5500](http://127.0.0.1:5500), so the browser treats them as completely separate origins with separate storage buckets.

6. Name something duplicated across your HTML pages. What problem does that duplication cause, and how might it be avoided?
The <header> navigation bar and <footer> are duplicated across every HTML page. This creates a maintenance burden where a single link or text update must be manually repeated in every file, increasing the risk of inconsistencies across pages. It can be avoided using server-side includes, a static site generator, or a shared JavaScript file that dynamically injects the header and footer.

