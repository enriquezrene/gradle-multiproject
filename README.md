# Gradle-multiproject

An multiproject example using gradle as build tool

childOne has not build.gradle file beacuse in Gradle build scripts are optional

The setting.gradle file contains the subprojects names
<ul>
<li><em>allprojects:</em> property to get a list with the current project and all its subprojects underneath it</li>
<li><em>subprojects:</em> provides a property to get the subprojects only.</li>
</ul>
A project can get more than defined properties (project properties defined in maven), if you want define an additional property use this sintax in the build.gradle file:
<pre>
ext.additionalPropertyName = propertyValue
</pre>

You can execute the child's tasks, for example:
childThree subproject has the task breakingTheLaw, inside the root project you can type:
<pre>
$ gradle breakingTheLaw
</pre>
output:
<pre>
I'm breaking the law
:childThree:breakingTheLaw UP-TO-DATE
BUILD SUCCESSFUL
Total time: 1.117 secs
</pre>
If you want to run just a project's task from the root you can use the absolute path:
<pre>
$ gradle :childOne:hello
</pre>
output:
<pre>
I'm breaking the law
:childOne:hello
I'm childOne
- My parent is root
- I'm adding an additional behaviour
- I'm an additional behaviour to other guys than childThree
- I am a good child.
</pre>
