# gradle-multiproject
An multiproject example using gradle as build tool

childOne has not build.gradle file beacuse in Gradle build scripts are optional

The setting.gradle file contains the subprojects names

allprojects: property to get a list with the current project and all its subprojects underneath it
subprojects: provides a property to get the subprojects only.

A project can get more than defined properties (project properties defined in maven), if you want define an additional property use this sintax in the build.gradle file:
ext.additionalPropertyName = propertyValue

You can execute the child's tasks, for example:
- childThree subproject has the task breakingTheLaw, inside the root project you can type:

$ gradle breakingTheLaw

output:

I'm breaking the law
:childThree:breakingTheLaw UP-TO-DATE

BUILD SUCCESSFUL

Total time: 1.117 secs

If you want to run just a project's task from the root you can use the absolute path:

$ gradle :childOne:hello

output:

I'm breaking the law
:childOne:hello
I'm childOne
- My parent is root
- I'm adding an additional behaviour
- I'm an additional behaviour to other guys than childThree
- I am a good child.

