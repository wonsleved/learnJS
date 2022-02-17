# Hello, world!

## The “script” tag

JavaScript programs can be inserted almost anywhere into an HTML document using the `<script>` tag.
The `<script>` tag contains JavaScript code which is automatically executed when the browser processes the tag.

## Modern markup

- **The `type` attribute: `<script type=…>`**
The old HTML standard, HTML4, required a script to have a `type`. Usually it was `type="text/javascript"`. It’s not required anymore.
- **The language attribute: `<script language=…>`**
There is no need to use it.

## External scripts

If we have a lot of JavaScript code, we can put it into a separate file.

Script files are attached to HTML with the `src` attribute:
```
<script src="/path/to/script.js"></script>
```

To attach several scripts, use multiple tags.

***As a rule, only the simplest scripts are put into HTML. More complex ones reside in separate files.
Browser downloads them only once and after that store them in cache.***

***If src is set, the script content is ignored.***
