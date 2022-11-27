<h1>W3C validator for Holberton School</h1>
<p>For HTML and CSS files.

Based on 2 APIs:</p>
<ul>
<li>https://validator.w3.org/nu/</li>
<li>http://jigsaw.w3.org/css-validator/validator</li>
</ul>
<h3>Installation<h3>
1. Clone this repo
<pre>git clone https://github.com/holbertonschool/W3C-Validator.git</pre>
2. Run shell script (see example in usage section below)

<h3>Usage:</h3>
Simple file:

<pre>./w3c_validator.py index.html</pre>
Multiple files:

<pre>./w3c_validator.py index.html header.html styles/common.css</pre>
All errors are printed in STDERR; Exit status = # of errors (0 on success)

<h4>References</h4>
https://developer.mozilla.org/en-US/
