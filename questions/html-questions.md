# HTML Questions:

* What does a `doctype` do?
  - `doctype` is put on the very top of an html file to let the browser know what version og html you are writing on your page. It should be the very first line of code in any html file.
* How do you serve a page with content in multiple languages?
  - Always use a language attribute on the html tag to declare the default language of the text in the page. When the page contains content in another language, add a language attribute to an element surrounding that content.
  - Use the lang attribute for pages served as HTML, and the xml:lang attribute for pages served as XML. For XHTML 1.x and HTML5 polyglot documents, use both together.
* What kind of things must you be wary of when design or developing for multilingual sites?
  - Message may not translate the same in different languages
  - Localizing content for different audiences
  - Allowing easy access to change languages
  - Left and right varies in different countries
* What are `data-` attributes good for?
  - `data-` is good for storing data in HTML for DOM parsing
  - To keep track on information
* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
  - Semantics: allowing you to describe more precisely what your content is.
  - Connectivity: allowing you to communicate with the server in new and innovative ways.
  - Offline and storage: allowing webpages to store data on the client-side locally and operate offline more efficiently.
  - Multimedia: making video and audio first-class citizens in the Open Web.
  - 2D/3D graphics and effects: allowing a much more diverse range of presentation options.
  - Performance and integration: providing greater speed optimization and better usage of computer hardware.
  - Device access: allowing for the usage of various input and output devices.
  - Styling: letting authors write more sophisticated themes.
* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
  - LocalStorage:
    - Web storage can be viewed simplistically as an improvement on cookies, providing much greater storage capacity. Available size is 5MB which considerably more space to work with than a typical 4KB cookie.
    - The data is not sent back to the server for every HTTP request (HTML, images, JavaScript, CSS, etc) - reducing the amount of traffic between client and server.
    - The data stored in localStorage persists until explicitly deleted. Changes made are saved and available for all current and future visits to the site.
    - It works on same-origin policy. So, data stored will only be available on the same origin.
  - Cookies:
    - We can set the expiration time for each cookie
    - The 4K limit is for the entire cookie, including name, value, expiry date etc. To support most browsers, keep the name under 4000 bytes, and the overall cookie size under 4093 bytes.
    - The data is sent back to the server for every HTTP request (HTML, images, JavaScript, CSS, etc) - increasing the amount of traffic between client and server.
  - sessionStorage:
    - It is similar to localStorage.
    - Changes are only available per window (or tab in browsers like Chrome and Firefox). Changes made are saved and available for the current page, as well as future visits to the site on the same window. Once the window is closed, the storage is deleted
    - The data is available only inside the window/tab in which it was set.
    - The data is not persistent i.e. it will be lost once the window/tab is closed. Like localStorage, it works on same-origin policy. So, data stored will only be available on the same origin.
* Describe the difference between `<script>`, `<script async>` and `<script defer>`.
  - A regular `<script>` tag will block rendering of the page, and the page will not continue to load until the script finishes.
  - `<script async>` will run the script asynchronously, meaning that it will not block rendering, but will run as soon as the script is available. This is usually intended for CDN files, or other such files, which do not change the page structure.
  - `<script defer>` will defer the script to run after the page is done parsing and before an onload event.
* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
  - You usually put the `<link>` tags in between the `<head>` to prevent Flash of Unstyled Content which gives the user something to look at while the rest of the page is being parsed.
  - Since Javascript blocks rendering by default, and the DOM and CSSOM construction can be also be delayed, it is usually best to keep scripts at the bottom of the page.
  - Exceptions are if you grab the scripts asynchronously, or at least defer them to the end of the page.
* What is progressive rendering?
  - Progressive rendering is a rendering mode in which the program gradually updates small parts of the entire image refining it from low quality to final result rather than focusing on one small part of the image at a time. The goal of progressive rendering is to always be able to see the process of refining the rendered image as a whole, pretty much like a painter sees his work evolve from a sketch by looking at the whole canvas after he adds more and more details.
* Why you would use a `srcset` attribute in an image tag? Explain the process the browser uses when evaluating the content of this attribute.
  - You would use the srcset attribute when you want to serve different images to users depending on their device display width - serve higher quality images to devices with retina display enhances the user experience while serving lower resolution images to low-end devices increase performance and decrease data wastage (because serving a larger image will not have any visible difference). For example: `<img srcset="small.jpg 500w, medium.jpg 1000w, large.jpg 2000w" src="..." alt="">` tells the browser to display the small, medium or large .jpg graphic depending on the client's resolution.
* Have you used different HTML templating languages before?
  - I have really good experience with Handlebars. It's a great way of filtering data coming from an ajax request!
