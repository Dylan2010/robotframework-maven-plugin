# Libdoc Goal 1.0.x #

Deprecated version. Valid only for 1.0.x branch

Runs the "libdoc" command to generate documentation of user libraries.
This script can generate keyword documentation in HTML and XML formats. The former is suitable for humans and the latter for RIDE, RFDoc, and other tools. This script can also upload XML documentation to RFDoc system.

Documentation can be created for both test libraries and resource files. All library and resource file types are supported, and also earlier generated documentation in XML format can be used as input.

## Usage ##

You can invoke `mvn robotframework:libdoc -DlibraryOrResourceDirectory=src/main/java/com/example/keywords` to generate documentation for user libraries contained in that package. The documentation, by default, goes to _${project.build.directory}/robot_.

## Plugin Parameters ##

| Name|	Type|	Since|	Description|
|:----|:----|:-----|:-----------|
|argument|	String|	-    |	Possible arguments that a library needs.|
|format|	String|	-	   |Specifies whether to generate HTML or XML output. The default value is HTML.|
|libraryOrResourceDirectory|	File|	-    |	Fully qualified path to the directory where the Java classes or resource files are located. e.g. src/main/java/com/test/|
| libraryOrResourceFile|	File|	-    |	Fully qualified path to the Java class (source code) or the resource file. e.g. src/main/java/com/test/ExampleLib.java|
|name |	String|	-    |	Sets the name of the documented library or resource.|
|output|	File|	-    |	Specifies where to write the generated documentation. If the given path is a directory, the documentation is written there using a file name like '`<name>.<format>`'. If a file with that name already exists, an index is added after the '`<name>`' part. If the given path is not a directory, it is used directly and possible existing files are overwritten. The default value for the path is the directory where the script is executed from. Default value is: ${project.build.directory}/robot.|
|styles|	String|	-	   |Overrides the default styles. If the given 'styles' is a path to an existing files, styles will be read from it. If it is string a 'NONE', no styles will be used. Otherwise the given text is used as-is.|
|title	|String|	-	   |Sets the title of the generated HTML documentation. Underscores in the given title are automatically converted to spaces.|

## Parameter Details ##

> <p><strong><a>argument</a>:</strong></p>
> <div>Possible arguments that a library needs.</div>
> <ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
<li><strong>Expression</strong>: <pre><code>${argument}</code></pre></li>
</blockquote><blockquote></ul>

<hr/>

<p><strong><a>format</a>:</strong></p>
<div>Specifies whether to generate HTML or XML output. The default value is HTML.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
<li><strong>Expression</strong>: <pre><code>${format}</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>libraryOrResourceDirectory</a>:</strong></p>
<div>Fully qualified path to the directory where the Java classes or resource files are located. e.g. src/main/java/com/test/</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.io.File</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
<li><strong>Expression</strong>: <pre><code>${libraryOrResourceDirectory}</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>libraryOrResourceFile</a>:</strong></p>
<div>Fully qualified path to the Java class (source code) or the resource file. e.g. src/main/java/com/test/ExampleLib.java</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.io.File</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
<li><strong>Expression</strong>: <pre><code>${libraryOrResourceFile}</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>name</a>:</strong></p>
<div>Sets the name of the documented library or resource.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
<li><strong>Expression</strong>: <pre><code>${name}</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>output</a>:</strong></p>
<div>Specifies where to write the generated documentation. If the given path is a directory, the documentation is written there using a file name like '<code>&lt;name&gt;.&lt;format&gt;</code>'. If a file with that name already exists, an index is added after the '&lt;name&gt;' part. If the given path is not a directory, it is used directly and possible existing files are overwritten. The default value for the path is the directory where the script is executed from.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.io.File</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
<li><strong>Expression</strong>: <pre><code>${output}</code></pre></li>
<li><strong>Default</strong>: <pre><code>${project.build.directory}/robot</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>styles</a>:</strong></p>
<div>Overrides the default styles. If the given 'styles' is a path to an existing files, styles will be read from it. If it is string a 'NONE', no styles will be used. Otherwise the given text is used as-is.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
<li><strong>Expression</strong>: <pre><code>${styles}</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>title</a>:</strong></p>
<div>Sets the title of the generated HTML documentation. Underscores in the given title are automatically converted to spaces.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
<li><strong>Expression</strong>: <pre><code>${title}</code></pre></li>
</blockquote></ul>