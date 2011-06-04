# 00

In this tutorial we start creating HTML documents and learn about some of the different Python filters.

Let's start by writing a short Python script:

{{ d['docs/tutorials/1-python/00/script.py|pyg'] }}

And a simple HTML file which includes it:

{{ d['docs/tutorials/1-python/00/doc.html|pyg'] }}

Here is the .dexy configuration to run this.

<pre>
{{ d['docs/tutorials/1-python/00/.dexy|dexy'] }}
</pre>

Then by running this:

{{ d['run-00.sh|idio']['run'] }}

You should generate a html file that looks like this:

<iframe src="00/doc.html" width="300px" height="200px">
</iframe>

# 01

Now that we're using HTML, let's make this output a little more colourful. We want to use syntax highlighting and apply a stylesheet. You must have Pygments installed (easy_install pygments). You can generate a stylesheet as follows:

{{ d['docs/tutorials/1-python/01/generate-stylesheet.sh|pyg'] }}

You can experiment with other styles besides 'pastie'.

Instead of putting our python script through a 'dexy' filter to show it as plain text, we want to run it through the 'pyg' filter which will apply syntax highlighting.

<pre>
{{ d['docs/tutorials/1-python/01/.dexy|dexy'] }}
</pre>

We also added a line so that the css file we created (from pygmentize) gets copied to our output directory. Now we can update the HTML file. We need to add a link to the stylesheet, and change the reference to the Python script to reflect our change to use pygments:

{{ d['docs/tutorials/1-python/01/doc.html|pyg'] }}

We want to run dexy with the -s filter to make the filenames nicer:

{{ d['run-01.sh|idio']['run'] }}

If you open the generated html file in a web browser, you should be able to see the Python source code with syntax highlighting. If not check that your relative paths to the stylesheet is correct. You can view source on the HTML or open the generated file in a text editor to check that the syntax highlighting markup is present.

<iframe src="01/doc.html" width="300px" height="200px">
</iframe>

# 02

Next we want to run the code. Add a line to the .dexy file:

<pre>
{{ d['docs/tutorials/1-python/02/.dexy|dexy'] }}
</pre>

And update the html file:

{{ d['docs/tutorials/1-python/02/doc.html|pyg'] }}

<iframe src="02/doc.html" width="300px" height="200px">
</iframe>

# 03

Now, let's change this so that instead of showing the code and, separately, showing the output, we just show a console transcript.

<pre>
{{ d['docs/tutorials/1-python/03/.dexy|dexy'] }}
</pre>

And update the html file:

{{ d['docs/tutorials/1-python/03/doc.html|pyg'] }}

Different filters can be used depending on which style of code presentation you like. Sometimes the console view is useful, other times you will only want to show the output.

<iframe src="03/doc.html" width="300px" height="200px">
</iframe>