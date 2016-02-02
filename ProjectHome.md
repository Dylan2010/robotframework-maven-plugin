# Robot Framework Maven Plugin #

> This project is no longer active. Please use the updated fork at [GitHub](https://github.com/robotframework/MavenPlugin)

[Maven](http://maven.apache.org) plugin for using the [Robot Framework](http://robotframework.googlecode.com). Goal of this plugin is to be able to use Robot Framework in a Maven project without the need to install anything extra (e.g. Robot Framework, Jython, etc). In short, it's a non-invasive way of introducing acceptance test driven development to your existing projects quickly.

## Maven Goals ##

The plugin currently has two goals:
  * **[run](RunGoal.md)** - behaves like invoking the "[jybot](http://robotframework.googlecode.com/svn/tags/robotframework-2.5.6/doc/userguide/RobotFrameworkUserGuide.html#starting-test-execution)" Robot Framework command for executing test cases
  * **[libdoc](LibdocGoal.md)** - invokes the "[libdoc.py](http://robotframework.googlecode.com/svn/tags/robotframework-2.5.6/tools/libdoc/doc/libdoc.html)" Robot Framework command for generating keyword documentation for test libraries and resource files

## Quick Start ##

Add the plugin to your build:

```
<project>

  <build>
    ..
    ..
    <plugins>
      ..
      ..

      <plugin>
        <groupId>com.googlecode.robotframework-maven-plugin</groupId>
        <artifactId>robotframework-maven-plugin</artifactId>
        <version>1.1.2</version>
        <executions>
          <execution>
            <goals>
              <goal>run</goal>
            </goals>
          </execution>
        </executions>        
      </plugin>

      ..
      ..
    </plugins>
  </build>

</project>
```

By default, you can add your test cases to _${project.basedir}/src/test/resources/robotframework/tests_

Third party libraries (e.g. Selenium Library) can be added to _${project.basedir}/src/test/resources/robotframework/libraries_

During _mvn install_ invocation, **run** command will be invoked during the _integration-test_ phase.

## News ##
  * Version 1.1.2 [Released](ReleaseNotes.md)
  * Version 1.1.1 [Released](ReleaseNotes.md)!
  * Welcome Dietrich Schulten! New contributor
  * Version 1.1 [Released](ReleaseNotes.md)!