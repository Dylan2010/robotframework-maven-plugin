# Using the Robot Framework Maven Plugin with Selenium Library #

_Since 1.1_

Starting version 1.1, a _extraPathDirectories_ parameter has been added to the plugin. You can use this to add extra test libraries to your build.

By default, you should add them to _${project.basedir}/src/test/resources/robotframework/libraries_



## Configuration and Installation ##

Download the tarball from the Selenium Library [download page](http://code.google.com/p/robotframework-seleniumlibrary/downloads/list), e.g. robotframework-seleniumlibrary-2.6.tar.gz

Extract the file and move the _SeleniumLibrary_ directory from _robotframework-seleniumLibrary/src_ to _${project.basedir}/src/test/resources/robotframework/libraries_.

So your project will have _yourProject/src/test/resources/robotframework/libraries/SeleniumLibrary_

Now, you can use Selenium Library Keywords to your tests.

e.g.

```
*** Settings ***
Library  SeleniumLibrary
Suite Set Up  Start Selenium Server
Suite Tear Down  Stop Selenium Server


*** Test Cases ***
My Test
   Open Browser  http://robotframework.googlecode.com
```