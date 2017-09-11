# HTML Questions

#### What does a `doctype` do?

It specifies which markup standard the page is using. With the information, the
browser determines how to render the page according to the page's source code.

#### What's the difference between standards mode and quirks mode?

They are modes used by browser rendering engines. In the standards mode, the
engine will render a page as HTML and CSS specifications specify. The quirks
mode is to render legacy pages written before these standards are fixed. The
legacy pages contain non-standard behaviours emulated in old browsers such as
Internet Explorer 5 or Navigator 4.

We can enforce browsers to use standards mode with a `<!DOCTYPE html>` tag.

#### What's the difference between HTML and XHTML?

Syntax differences developed by different organizations. HTML is SGML-based
while XHTML is XML-based. And XHTML is more strict than HTML, therefore HTML
can look different in different browsers while XHTML look the same.

http://www.diffen.com/difference/HTML_vs_XHTML

#### Are there any problems with serving pages as `application/xhtml+xml`?

IE < 8 will show a download dialog for the pages, instead of rendering them
properly.

#### How do you serve a page with content in multiple languages?

Use `lang` (or `xml:lang` for XHTML) in tags. Also metadata and
`Content-Language` HTTP header can be used.

#### What kind of things must you be wary of when design or developing for multilingual sites?

- `hreflang` attr in link
- `dir` attr indicating language direction, such as `rtl`
- `<meta charset='UTF-8'>`
- `font-size` for `:lang({language_code})` selectors in CSS
- difference in word langth for each language

#### What are `data-` attributes good for?

It makes HTML elements contain extra information without using non-standard
attributes, or other hacks like that.

#### Consider HTML5 as an open web platform. What are the building blocks of HTML5?

The main building blocks are centered on HTML 5, CSS3, JavaScript and SVG.
Where HTML is a language to define the mark-up of a document (titles, headers,
body, footer, tables, input forms etc.), CSS is a language to define style
(formatting, colors, shades and the like). JavaScript is a programming/scripting
language and SVG is a language for creating 2D scalable vector graphics and
images.

http://yucianga.info/?p=655

#### Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.

They are all storage on the client side. Cookies is small piece of key-value
pair with a expire time, sessionStorage is on persistent and scope only to
current windows, localStorage is persistent and scope only to domain, by
key-value pair or SQL database (Web SQL)

#### Can you explain the difference between GET and POST?

They are two types of HTTP requests. GET represents a specific resource. Should
not have and side effect like insert/update because they may be requested by
robots. GET use URL the send data. AJAX GET in IE will be cached, so to ensure
data updates, better add a timestamp

POST represent actions on resources, like insert/update/delete. They usually
sent from HTML form. Lareg data could be sent by POST. Data is send along with
HTTP header, instead of data of GET in the URL.

http://stackoverflow.com/questions/3477333/what-is-the-difference-between-post-and-get

#### Describe the difference between `<script>`, `<script async>` and `<script defer>`.

- `<script>` stops rendering process, and download and run a script.
- `<script async>` don't stop rendering process while asynchronously
  downloading a script. When finishing download, it stops rendering and runs the
  script.
- `<script defer>` don't stop rendering process while asynchronously
  downloading a script. When finishing rendering, it runs the script.

#### Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?

Putting stylesheets in the HEAD allows the page to render progressively, that is,
we want the browser to display whatever content it has as soon as possible. Putting
stylesheets near the bottom of the document would prohibit progressive rendering
in many browsers, including Internet Explorer. These browsers block rendering to
avoid having to redraw elements of the page if their styles change. The user is
stuck viewing a blank white page.

Putting scripts at the bottom of body may block parallel downloads and rendering,
and it can delay rendering.

https://stackoverflow.com/questions/6625773/where-should-i-put-the-css-and-javascript-code-in-an-html-webpage

#### What is progressive rendering?

When a HTTP response is flushed multiple times, a browser doesn't wait until
the whole content is loaded and renders each part earlier.

#### Have you used different HTML templating languages before?

Yes. Jinja2 and Django template language in Python. Jade and EJS in JavaScript.
Some more in other languages.
