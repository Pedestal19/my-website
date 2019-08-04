# This file is just a readme file
__purpose__
# Initializr - Documentation
# august update

## Download or Print

Edit on example branch

Updates on master on github before rebase



# purpose

this is no ordinary read me file


Let's take a look at what contains <a href="https://github.com/verekia/initializr/tree/master/war/builder/modules/modernizr">modules/modernizr</a> on the Git repo:
<ul>
	<li><code>modernizr-2.0.min.js</code> - It's the actual Modernizr JS file,</li>
	<li><code>modernizr.html</code> - It's the file containing the HTML JavaScript code inclusion,</li>
	<li><code>modernizr.json</code> - Here is the interesting stuff! Let's take a closer look at this file:</li>
</ul> 

<pre>
{
	"author" : "Paul Irish",
	"name" : "Modernizr",
	"id" : "modernizr",
	"inserts" :
	[
		{
			"what" : "modernizr.html",
			"where" : "index.html/head/html5polyfill"
		}
	,
		{
			"what" : "modernizr-2.0.min.js",
			"where" : "js/libs/modernizr-2.0.min.js",
			"type" : "file"
		}
	],
	"incompatibilities" : ["html5shiv"]
}
</pre>

We can see that a module configuration file is actually a simple JSON containing the following members:
<ul>
	<li><code>author</code>: The name of the author of the module,</li>
	<li><code>name</code>: The "Fancy name" of the module,</li>
	<li><code>id</code>: The unique id of the module (prefixed with h5bp- or izr- if it's from HTML5 Boilerplate or Initializr),</li>
	<li><code>incompatibilities</code>: An array of modules ids that can't be used with this one.</li>
	<li><code>inserts</code>: An array of insertions of code snippets or files with the following fields:</li>
	<ul>
		<li><code>what</code>: What code snippet or file is going to be included in the archive (refers to an other file of the same module folder),</li>
		<li><code>where</code>: In which file and place the code snippet will be injected (<a href="https://github.com/verekia/initializr/tree/master/war/builder/templates">in these files</a>), or the name of the file if it's an entire file,</li>
		<li><code>type</code>: (optional) specify <code>file</code> for this field if the current insertion is an entire file (like modernizr JS file).</li>
	</ul>
</ul>
