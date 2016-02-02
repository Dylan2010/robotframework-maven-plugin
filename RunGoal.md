# Run Goal #

_Available since version 1.1. Drop in replacement for the "jybot" goal in the 1.0.x branch._

Behaves like invoking the "jybot" command.

Robot Framework test cases are created in files and directories, and they are executed by configuring the path to the file or directory in question to the _testCasesDirectory_ configuration. The given file or directory creates the top-level test suite, which gets its name, unless overridden with the "name" option, from the file or directory name.


## Usage ##

By default, test cases located at _${project.basedir}/src/test/resources/robotframework_ will run during the _integration-test_ phase.

If for example you want to run test cases in a different path, say _${project.basedir}/src/main/resources/robot_, configure your pom as so:

```
      <plugin>
        <groupId>com.googlecode.robotframework-maven-plugin</groupId>
        <artifactId>robotframework-maven-plugin</artifactId>
        <version>1.1.1</version>
        <executions>
          <execution>
            <goals>
              <goal>run</goal>
            </goals>
          </execution>
        </executions>
        <configuration>
          <testCasesDirectory>${project.basedir}/src/main/resources/robot</testCasesDirectory>
        </configuration>
      </plugin>
```

Generated reports are written to _${project.build.directory}/robotframework_ by default. This could be overridden by configuring the _outputDirectory_ configuration.

Check out [this page](http://code.google.com/p/robotframework-maven-plugin/wiki/UseWithSeleniumLibrary) for instructions on using with third-party plugins.

## Plugin Parameters ##

| Name |	Type	|Since|	Description|
|:-----|:-----|:----|:-----------|
|argumentFile|	File |	-	  |A text file to read more arguments from.|
|combinedTagStats|	List |	-	  |Creates combined statistics based on tags. Use the format "tags:title"|
|criticalTags|	List |	-   |	Tests that have the given tags are considered critical.|
|debugFile|	File |	-	  |A debug file that is written during execution.|
|document|	String|	-   |	Sets the documentation of the top-level tests suites.|
|excludes|	List |	-   |	Selects the tests cases by tags.|
|extraPathDirectories|	File`[]`	|1.1	 |Additional locations (directories, ZIPs, JARs) where to search test libraries from when they are imported. Maps to Jybot's --pythonpath option. Otherwise if no locations are declared, the default location is ${project.basedir}/src/test/resources/robotframework/libraries.|
|includes|	List |	-   |	Selects the tests cases by tags.|
|listeners|	List |	-   |	Sets listeners for monitoring tests execution. Use the format "ListenerWithArgs:arg1:arg2" or simply "ListenerWithoutArgs"|
|log   |	File |	-	  |Sets the path to the generated log file.|
|logLevel|	String|	-   |	Sets the threshold level for logging.|
|logTitle	|String|	-   |	Sets a title for the generated tests log.|
|metadata|	List |	-   |	Sets free metadata for the top level tests suites.|
|monitorColors|	String|	1.1 |	Using ANSI colors in console. Normally colors work in unixes but not in Windows. Default is 'on'. 'on' - use colors in unixes but not in Windows. 'off' - never use colors. 'force' - always use colors (also in Windows)|
|monitorWidth|	String|	-   |	Width of the monitor output. Default is 78.|
|name  |	String|	-	  |Sets the name of the top-level tests suites.|
|nonCriticalTags|	List |	-   |	Tests that have the given tags are not critical.|
|output|	File |	-   |	Sets the path to the generated output file.|
|outputDirectory|	File |	-   |	Configures where generated reports are to be placed. Default value is: ${project.build.directory}/robotframework.|
|report|	File |	-   |	Sets the path to the generated report file.|
|reportBackground|	String|	-   |	Sets background colors for the generated report and summary.|
|reportTitle|	String|	-   |	Sets a title for the generated tests report.|
|runMode|	String|	-   |	Sets the execution mode for this tests run. Valid modes are ContinueOnFailure, ExitOnFailure, SkipTeardownOnExit, DryRun, and Random:&lt;what&gt;.|
|skip  |	boolean|	1.1 |	Skip tests, bound to -Dmaven.test.skip, which suppresses test compilation as well. Default value is: false.|
|skipATs	|boolean|	1.1 |	Skip acceptance tests executed by this plugin.|
|skipITs	|boolean|	1.1 |	Skip acceptance tests executed by this plugin together with other integration tests, e.g. tests run by the maven-failsafe-plugin.|
|skipTests|	boolean|	1.1 |	Skip tests.|
|splitOutputs|	String|	-   |	Splits output and log files.|
|suiteStatLevel|	String|	-   |	Defines how many levels to show in the Statistics by Suite table in outputs.|
|suites|	List |	-   |	Selects the tests suites by name.|
|summary|	File |	-   |	Sets the path to the generated summary file.|
|summaryTitle|	String|	-   |	Sets a title for the generated summary report.|
|tagDocs|	List |	-   |	Adds documentation to the specified tags.|
|tagStatExcludes|	List |	-   |	Excludes these tags from the Statistics by Tag and Test Details by Tag tables in outputs.|
|tagStatIncludes|	List |	-   |	Includes only these tags in the Statistics by Tag and Test Details by Tag tables in outputs.|
|tagStatLinks|	List |	-   |	Adds external links to the Statistics by Tag table in outputs. Use the format "pattern:link:title"|
|tags  |	List |	-   |	Sets the tags(s) to all executed tests cases.|
|testCasesDirectory|	File |	-   |	The directory where the tests cases are located. Default value is: ${project.basedir}/src/test/resources/robotframework/tests.|
|tests |	List |	-   |	Selects the tests cases by name.|
|timestampOutputs	|boolean|	-   |	Adds a timestamp to all output files.|
|variableFiles|	List |	-   |	Sets variables using variables files. Use the format "path:args"|
|variables|	List |	-   |	Sets individual variables. Use the format "name:value"|
|warnOnSkippedFiles|	boolean|	-   |	Show a warning when an invalid file is skipped.|
|xunitFile	|File  |	-	  |Sets the path to the generated XUnit compatible result file|

## Parameter Details ##

> <p><strong><a>argumentFile</a>:</strong></p>
> <div>A text file to read more arguments from.</div>
> <ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.io.File</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote><blockquote></ul>

<hr/>

<p><strong><a>combinedTagStats</a>:</strong></p>
<div>Creates combined statistics based on tags. Use the format "tags:title"</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>criticalTags</a>:</strong></p>
<div>Tests that have the given tags are considered critical.</div>
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
<div>Sets the documentation of the top-level tests suites.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>excludes</a>:</strong></p>
<div>Selects the tests cases by tags.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>extraPathDirectories</a>:</strong></p>
<div>Additional locations (directories, ZIPs, JARs) where to search test libraries from when they are imported. Maps to Jybot's --pythonpath option. Otherwise if no locations are declared, the default location is ${project.basedir}/src/test/resources/robotframework/libraries.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.io.File[]</code></pre></li>
<li><strong>Since</strong>: <pre><code>1.1</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>includes</a>:</strong></p>
<div>Selects the tests cases by tags.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>listeners</a>:</strong></p>
<div>Sets listeners for monitoring tests execution. Use the format "ListenerWithArgs:arg1:arg2" or simply "ListenerWithoutArgs"</div>
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
<div>Sets a title for the generated tests log.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>metadata</a>:</strong></p>
<div>Sets free metadata for the top level tests suites.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>monitorColors</a>:</strong></p>
<div>Using ANSI colors in console. Normally colors work in unixes but not in Windows. Default is 'on'.<br>
<blockquote><ul>
<blockquote><li>'on' - use colors in unixes but not in Windows</li>
<li>'off' - never use colors</li>
<li>'force' - always use colors (also in Windows)</li>
</blockquote></blockquote><blockquote></ul>
</blockquote></div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Since</strong>: <pre><code>1.1</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>monitorWidth</a>:</strong></p>
<div>Width of the monitor output. Default is 78.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>name</a>:</strong></p>
<div>Sets the name of the top-level tests suites.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>nonCriticalTags</a>:</strong></p>
<div>Tests that have the given tags are not critical.</div>
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
<li><strong>Default</strong>: <pre><code>${project.build.directory}/robotframework</code></pre></li>
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
<div>Sets a title for the generated tests report.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>runMode</a>:</strong></p>
<div>Sets the execution mode for this tests run. Valid modes are ContinueOnFailure, ExitOnFailure, SkipTeardownOnExit, DryRun, and Random:&lt;what&gt;.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>skip</a>:</strong></p>
<div>Skip tests, bound to -Dmaven.test.skip, which suppresses test compilation as well.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>boolean</code></pre></li>
<li><strong>Since</strong>: <pre><code>1.1</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
<li><strong>Expression</strong>: <pre><code>${maven.test.skip}</code></pre></li>
<li><strong>Default</strong>: <pre><code>false</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>skipATs</a>:</strong></p>
<div>Skip acceptance tests executed by this plugin.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>boolean</code></pre></li>
<li><strong>Since</strong>: <pre><code>1.1</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
<li><strong>Expression</strong>: <pre><code>${skipATs}</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>skipITs</a>:</strong></p>
<div>Skip acceptance tests executed by this plugin together with other integration tests, e.g. tests run by the maven-failsafe-plugin.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>boolean</code></pre></li>
<li><strong>Since</strong>: <pre><code>1.1</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
<li><strong>Expression</strong>: <pre><code>${skipITs}</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>skipTests</a>:</strong></p>
<div>Skip tests.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>boolean</code></pre></li>
<li><strong>Since</strong>: <pre><code>1.1</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
<li><strong>Expression</strong>: <pre><code>${skipTests}</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>splitOutputs</a>:</strong></p>
<div>Splits output and log files.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.lang.String</code></pre></li>
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

<p><strong><a>suites</a>:</strong></p>
<div>Selects the tests suites by name.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
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

<p><strong><a>tagDocs</a>:</strong></p>
<div>Adds documentation to the specified tags.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>tagStatExcludes</a>:</strong></p>
<div>Excludes these tags from the Statistics by Tag and Test Details by Tag tables in outputs.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>tagStatIncludes</a>:</strong></p>
<div>Includes only these tags in the Statistics by Tag and Test Details by Tag tables in outputs.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>tagStatLinks</a>:</strong></p>
<div>Adds external links to the Statistics by Tag table in outputs. Use the format "pattern:link:title"</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>tags</a>:</strong></p>
<div>Sets the tags(s) to all executed tests cases.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>testCasesDirectory</a>:</strong></p>
<div>The directory where the tests cases are located.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.io.File</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
<li><strong>Default</strong>: <pre><code>${project.basedir}/src/test/resources/robotframework/tests</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>tests</a>:</strong></p>
<div>Selects the tests cases by name.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>timestampOutputs</a>:</strong></p>
<div>Adds a timestamp to all output files.</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>boolean</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>variableFiles</a>:</strong></p>
<div>Sets variables using variables files. Use the format "path:args"</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.util.List</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>

<hr/>

<p><strong><a>variables</a>:</strong></p>
<div>Sets individual variables. Use the format "name:value"</div>
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
<div>Sets the path to the generated XUnit compatible result file</div>
<ul>
<blockquote><li><strong>Type</strong>: <pre><code>java.io.File</code></pre></li>
<li><strong>Required</strong>: <pre><code>No</code></pre></li>
</blockquote></ul>