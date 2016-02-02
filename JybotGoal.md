# Jybot Goal #

Behaves like invoking the "jybot" command.

Robot Framework test cases are created in files and directories, and they are executed by configuring the path to the file or directory in question to the _testCasesDirectory_ configuration. The given file or directory creates the top-level test suite, which gets its name, unless overridden with the "name" option, from the file or directory name.


## Usage ##

By default, test cases located at _${project.basedir}/src/test/resources/robot_ gets run during the _integration-test_ phase.

If for example you want to run test cases in a different path, say _${project.basedir}/src/main/resources/robot_, configure your pom as so:

```
      <plugin>
        <groupId>com.googlecode</groupId>
        <artifactId>robotframework-maven-plugin</artifactId>
        <version>1.0.1</version>
        <executions>
          <execution>
            <goals>
              <goal>jybot</goal>
            </goals>
          </execution>
        </executions>
        <configuration>
          <testCasesDirectory>${project.basedir}/src/main/resources</testCasesDirectory>
        </configuration>
      </plugin>
```

Generated reports are written to _${project.build.directory}/robot_ by default. This could be overridden by configuring the _outputDirectory_ configuration.

## Plugin Parameters ##

| Name  |	Type |	Since |	Description |
|:------|:-----|:------|:------------|
| argumentFile |	File	| -	    | A text file to read more arguments from. |
| critical |	List |	-	    | Tests that have the given tag are considered critical.|
| debugFile	| File	| -     | 	A debug file that is written during execution.|
| document |	String|	-	    |Sets the documentation of the top-level test suite.|
| exclude|	List	|-	     |Selects the test cases by tag.|
| include	|List  |	-     |	Selects the test cases by tag.|
| listener|	List	|-      |	Sets a listener for monitoring test execution. Use the format "ListenerWithArgs:arg1:arg2" or simply "ListenerWithoutArgs"|
| log	  |File  |	-	    |Sets the path to the generated log file.|
| logLevel|	String	|-	     |Sets the threshold level for logging.|
| logTitle	|String|	-	    |Sets a title for the generated test log.|
| metadata|	List |	-	    |Sets free metadata for the top level test suite.|
| name	 |String	|-	     |Sets the name of the top-level test suite.|
| nonCritical	|List	 |-      |	Tests that have the given tag are not critical.|
| output |	File	|-	     |Sets the path to the generated output file. |
| outputDirectory	| File |	-     | Configures where generated reports are to be placed. Default value is: ${project.build.directory}/robot. |
| report|	File |	-     |	Sets the path to the generated report file.|
| reportBackground	|String|	-     |	Sets background colors for the generated report and summary.|
| reportTitle|	String|	-	    |Sets a title for the generated test report.|
| runMode|	String	|-	     |Sets the execution mode for this test run. Valid modes are ContinueOnFailure, ExitOnFailure, SkipTeardownOnExit, DryRun, and Random:`<what>`.|
| splitOutputs|	String|	-     |	Splits output and log files.|
| suite |	List |	-	    |Selects the test suites by name.|
| suiteStatLevel	|String|	-     |	Defines how many levels to show in the Statistics by Suite table in outputs.|
| summary	|File	 |-	     |Sets the path to the generated summary file.|
| summaryTitle|	String|	-	    |Sets a title for the generated summary report.|
| tag   |	List |	-     |	Sets the tag(s) to all executed test cases.|
| tagDoc|	List |	-     |	Adds documentation to the specified tags.|
| tagStatCombine|	List	|-	     |Creates combined statistics based on tags. Use the format "tags:title"|
| tagStatExclude	|List  |	-	    |Excludes these tags from the Statistics by Tag and Test Details by Tag tables in outputs.|
| tagStatInclude	|List  |	-	    |Includes only these tags in the Statistics by Tag and Test Details by Tag tables in outputs.|
| tagStatLink|	List |	-	    |Adds external links to the Statistics by Tag table in outputs. Use the format "pattern:link:title"|
| test  |	List |	-	    |Selects the test cases by name.|
| testCasesDirectory|	File	|-	     |The directory where the test cases are located. Default value is: ${project.basedir}/src/test/resources/robot.|
| timestampOuputs	|boolean|	-	    |Adds a timestamp to all output files.|
| variable|	List |	-	    |Sets individual variables. Use the format "name:value"|
| variableFile|	List |	-     |	Sets variables using variable files. Use the format "path:args"|
| warnOnSkippedFiles|	boolean|	-	    |Show a warning when an invalid file is skipped.|
| xunitFile|	File |	-	    |Sets the path to the generated XUnit compatible result file. New in Robot Framework 2.5.5.|

## Parameter Details ##

> <p><strong><a>argumentFile</a>:</strong></p>
> <div>A text file to read more arguments from.</div>
> <ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.io.File</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote><blockquote></ul>

<hr/>

<p><strong><a>critical</a>:</strong></p>
<div>Tests that have the given tag are considered critical.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>debugFile</a>:</strong></p>
<div>A debug file that is written during execution.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.io.File</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>document</a>:</strong></p>
<div>Sets the documentation of the top-level test suite.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>exclude</a>:</strong></p>
<div>Selects the test cases by tag.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>include</a>:</strong></p>
<div>Selects the test cases by tag.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>listener</a>:</strong></p>
<div>Sets a listener for monitoring test execution. Use the format "ListenerWithArgs:arg1:arg2" or simply "ListenerWithoutArgs"</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>log</a>:</strong></p>
<div>Sets the path to the generated log file.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.io.File</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>logLevel</a>:</strong></p>
<div>Sets the threshold level for logging.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>logTitle</a>:</strong></p>
<div>Sets a title for the generated test log.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>metadata</a>:</strong></p>
<div>Sets free metadata for the top level test suite.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>name</a>:</strong></p>
<div>Sets the name of the top-level test suite.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>nonCritical</a>:</strong></p>
<div>Tests that have the given tag are not critical.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>output</a>:</strong></p>
<div>Sets the path to the generated output file.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.io.File</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>outputDirectory</a>:</strong></p>
<div>Configures where generated reports are to be placed.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.io.File</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
<li><strong>Default</strong>: <pre><code>${project.build.directory}/robot</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>report</a>:</strong></p>
<div>Sets the path to the generated report file.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.io.File</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>reportBackground</a>:</strong></p>
<div>Sets background colors for the generated report and summary.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>reportTitle</a>:</strong></p>
<div>Sets a title for the generated test report.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>runMode</a>:</strong></p>
<div>Sets the execution mode for this test run. Valid modes are ContinueOnFailure, ExitOnFailure, SkipTeardownOnExit, DryRun, and Random:&lt;what&gt;.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>splitOutputs</a>:</strong></p>
<div>Splits output and log files.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>suite</a>:</strong></p>
<div>Selects the test suites by name.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>suiteStatLevel</a>:</strong></p>
<div>Defines how many levels to show in the Statistics by Suite table in outputs.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>summary</a>:</strong></p>
<div>Sets the path to the generated summary file.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.io.File</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>summaryTitle</a>:</strong></p>
<div>Sets a title for the generated summary report.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>tag</a>:</strong></p>
<div>Sets the tag(s) to all executed test cases.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>tagDoc</a>:</strong></p>
<div>Adds documentation to the specified tags.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>tagStatCombine</a>:</strong></p>
<div>Creates combined statistics based on tags. Use the format  "tags:title"</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>tagStatExclude</a>:</strong></p>
<div>Excludes these tags from the Statistics by Tag and Test Details by Tag tables in outputs.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>tagStatInclude</a>:</strong></p>
<div>Includes only these tags in the Statistics by Tag and Test Details by Tag tables in outputs.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>tagStatLink</a>:</strong></p>
<div>Adds external links to the Statistics by Tag table in outputs. Use the format "pattern:link:title"</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>test</a>:</strong></p>
<div>Selects the test cases by name.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>testCasesDirectory</a>:</strong></p>
<div>The directory where the test cases are located.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.io.File</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
<li><strong>Default</strong>: <pre><code>${project.basedir}/src/test/resources/robot</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>timestampOuputs</a>:</strong></p>
<div>Adds a timestamp to all output files.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>boolean</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>variable</a>:</strong></p>
<div>Sets individual variables. Use the format "name:value"</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>variableFile</a>:</strong></p>
<div>Sets variables using variable files. Use the format "path:args"</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>warnOnSkippedFiles</a>:</strong></p>
<div>Show a warning when an invalid file is skipped.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>boolean</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>xunitFile</a>:</strong></p>
<div>Sets the path to the generated XUnit compatible result file.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.io.File</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>