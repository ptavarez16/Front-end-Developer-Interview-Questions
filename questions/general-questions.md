# General Questions:

### What did you learn yesterday/this week?
This week, I started a React.js tutorial. The tutorial instructs developers how to build a tic-tac-toe game using React. I've gotten a refresher on what JSX and components are, and I learned how to get started with the Create React App.

### What excites or interests you about coding?
What interests me the most about coding is always being in the position to learn something new. Being able to pick up a new tool and apply it to an application to solve a problem is a such a thrilling feeling. The challenge of solving a problem through research takes patience, but once you find the right answer it brings with it a great high!

### When building a new web site or maintaining one, can you explain some techniques you have used to increase performance?
When building a new web site, some techniques I use to increase performance are:
    - Clean up the HTML document
      - Proper CSS placement
      - Proper JS placement
    - Optimize CSS performance
    - Reduce external HTTP requests
    - Minify CSS, JS, and HTML files
    - Use a framework

### Can you describe some SEO best practices or techniques you have used lately?
  1. Title tags
  2. Meta descriptions
  3. Content with targeted keyword phrases
  4. Header tags and keywprd phrases
  5. Internal page linking with anchor text
  6. Image ALT tags and filenames
  7. Make content easy to read

### Can you explain any common techniques or recent issues solved in regards to front-end security?

### What actions have you personally taken on recent projects to increase maintainability of your code?
To maintain my code, one thing I am a huge fan of is version control. With git, I commit frequently to ensure I have backups to all of my code. If I break something, I can easily jump back in time and go back to code I know works.

Writing clean and legible code is also key in increasing maintainability. I strive to write code that I anyone will be able to see and know exactly what's going on.

### Talk about your preferred development environment.
Tech:
    
    I'll like to be part of a team that follows the three server tiers, called development, staging and production (DSP).
    During the developer server, developers test code and check whether the application runs successfully with that code. Once everything is running smoothly, it's time to move to the staging server.
    The staging server is optimized to look and work just like the production server. This step is to reinforce testing and confirm that the new code does not break the old code or cause new bugs. Once this is approved by the team to deploy, it's off to the production server.
    The production server is the last step. Once the approval is done, the application then becomes part of this server.

### Which version control systems are you familiar with?
I am familiar with Git and GitHub.

### Can you describe your workflow when you create a web page?
Planning:
  - wireframe
  - user stories
Set up:
  - Create an API Template
  - Deploy and ensure everything is working as it should
  - Create a client template
  - Deploy and ensure I could comminicate with the API

API:
  - Create resources and end points
  - Test resource's end points with curl scripts

Client:
  - Add basic UI components
  - CRUD resources
  - Add styling
  
Final Touches:
  - Troubleshoot/Debug
  - Style
  - Documentation
  - README


### If you have 5 different stylesheets, how would you best integrate them into the site?
 If the 5 style sheets were all application specific, I'd combine them into one file. If they were a combination of application specific style sheets and libraries (like Bootstrap), I'd only combine the application specific ones.
 
 With Sass, I could simply import the different files into the main scss file that is being called by the application!

### Can you describe the difference between progressive enhancement and graceful degradation?
Progressive enhancement refers to a feature of your web site that enhances the experience for browsers that support it, but has no impact if your browser does not. As an example - consider IndexedDB. It lets you store data in a client-side database. If my web site made use of Ajax to load a large amount of data, I could use IndexedDB to cache data. If your browser doesn’t support IndexedDB, then we just do Ajax to load that data. Modern browsers get a benefit, older browsers don’t get screwed.

On the flip side, graceful degradation takes that modern feature and acts as if it is the default, but will not completely break the older browser. So in this case, the use of IndexedDB would be considered “normal”, not the additional benefit for the modern browser.

In my opinion, it comes down to one side where you build for a certain base and provide additional, not-required features for better browsers (progressive enhancement) versus building for the more modern browser that assumes certain features, but assuring they “break” well.

### How would you optimize a website's assets/resources?
1. Make fewer HTTP requests
2. Use a Content Delivery Network
3. Put CSS on top
4. Move scripts to the bottom
5. Make JS and CSS external
6. Avoid redirects
7. Remove duplicate scripts
  
### How many resources will a browser download from a given domain at a time?
This answer depends per browser. For Chrome it is 6, Firefox 6, IE11 is 8 though. I’d assume 6 then as a good average.
  #### What are the exceptions?
So the limits are per domain, so in theory, you could use a wildcard DNS where *.foo.com points to the same IP address.

### Name 3 ways to decrease page load (perceived or actual load time).
- Use minifier and gzip to decrease the page size - actual
- Show spinner or progress bar - perceived
- Preload the page before actually loading it using libraries like InstantClick - both actual and perceived
  
### If you jumped on a project and they used tabs and you used spaces, what would you do?
I’d follow the project norm. I personally prefer tabs, but when working on a project, I’m going to follow the standards/guidelines/etc that everyone is following. If it was for something important and not cosmetic, I’d bring it up for discussion of course.
  
### Describe how you would create a simple slideshow page.
 I would download bootstrap and use their carousel component if I wanted to make a simple slideshow page as soon as possible.
 
### If you could master one technology this year, what would it be?
If I could master one technology this year, it would be React. React uses HTML, CSS, and JavaScript... So I feel like mastering React would be like mastering those three and then some.

### Explain the importance of standards and standards bodies.
The relevance of web standards is most obvious when considering the emergence of new technologies. Where are these new tools going to belong? How do we structure them? What are they here for? The use of standards automatically makes every page you build genuinely cross-browser and cross-platform. With the use of web standards web designers, developers and engineers will be able to achieve a more stable web despite the ongoing introduction of new hardware and software. With the use of standards, both development and maintenance time become reduced as a result of faster debugging and troubleshooting when it comes to handling the code we create. Standards allow backwards compatibility and validation since they are written to be compliant with older browser versions. This compliant code can be validated through a validation service which makes the developer’s work a lot easier resulting in less production time. In addition to the previously mentioned benefits, the use of standards can also increase search engine success while also allowing for the certainty of graceful degradation.

### What is Flash of Unstyled Content? How do you avoid FOUC?
  A flash of unstyled content (FOUC, also flash of unstyled text or FOUT) is an instance where a web page appears briefly with the browser's default styles prior to loading an external CSS stylesheet, due to the web browser engine rendering the page before all information is retrieved. The page corrects itself as soon as the style rules are loaded and applied; however, the shift may be distracting.
  
  Solution:
  ```html
  <style type="text/css">
      .no-fouc {display: none;}
  </style>

  <script type="text/javascript">
      document.documentElement.className = 'no-fouc';
      // add to document ready: $('.no-fouc').removeClass('no-fouc');
  </script>
  ```
  
### Explain what ARIA and screenreaders are, and how to make a website accessible.
Accessible Rich Internet Applications (ARIA)  is a set of attributes that define ways to make Web content and Web applications (especially those developed with Ajax, JavaScript and more recent web technologies like Bootstrap) more accessible to people with disabilities. For example, ARIA enables accessible navigation landmarks, JavaScript widgets, form hints and error messages, live content updates, and more.
  
### Explain some of the pros and cons for CSS animations versus JavaScript animations.
Functionality:

In terms of functionality, CSS and Javascript are fairly similar. Both are able to do very impressive animations but it becomes more of a question of what exactly the animation needs to do. Animating using CSS is known as a declarative approach while Javascript is imperative. What this means is in CSS you must specify specifically what has to happen, while in Javascript you are able to programmatically define the animation.This means you have more control over an animation when using Javascript. For example, playing a complicated animation in reverse would be difficult in CSS as you would need to specify additional transition properties on every piece of the animation.

Overhead:

Javascript and CSS have a key difference, which is overhead. CSS is the same in every development environment and it is simple to learn and fairly straightforward. Javascript, on the other hand, is almost the opposite. Although basic Javascript has animation functionality, most animation is done through an additional library such as GSAP or velocity.js. Developers who are familiar with one library may not be familiar with another, meaning much development time must be spent on training. Additionally, many development environments may be using another Javascript library such as JQuery for non-animation development, which will lead to conflicts as many Javascript libraries are not compatible. Therefore, when developing it is important to consider the overhead cost of Javascript libraries.

Performance:

Performance is another important consideration, especially if developing on mobile platforms. CSS has fairly good performance as it offloads animation logic onto the browser itself. This lets the browser optimize DOM interaction and memory consumption and most importantly, uses the GPU to improve performance. On the other hand, Javascript performance can range from reasonably faster to much slower than CSS. Javascript performance depends on the library used and puts the burden on the developer to optimize. For example, JQuery is a commonly used library but is notorious for slow animation performance because it is not designed with animation in mind. Also, adding Javascript libraries creates more overhead and can increase page load times especially for mobile devices. There are lightweight libraries out there specifically for this issue, but lightweight libraries also have less functionality. As mentioned before, you may have to optimize performance which is completely dependent on the library being used. Using CSS or Javascript for animation is highly dependent on what you are trying to do. Javascript can be very powerful but is completely unnecessary if all you are doing is something like fading in a pop up window. Most of the time just using CSS is enough, but complicated animations can be difficult to do without using Javascript. If you decide to use Javascript, make sure to pick a suitable library which does not conflict with other libraries you may already be using.
  
### What does CORS stand for and what issue does it address?
Cross Origin Resource Sharing.

This is all because of javascript. On the web, it’s a huge risk to have javascript running that you can’t confirm came from the right source. Taken from wikipedia: “In computing, the same-origin policy is an important concept in the web application security model. Under the policy, a web browser permits scripts contained in a first web page to access data in a second web page, but only if both web pages have the same origin. An origin is defined as a combination of URI scheme, hostname, and port number.

This policy prevents a malicious script on one page from obtaining access to sensitive data on another web page through that page's Document Object Model.“

This can be pretty limiting… so for instance say you want to send and receive data to and from multiple servers and make say a single page application, this is where CORS comes in.

CORS allows resource sharing from across a different origin, or cross-domain requests.
  
