when downloading Maven, it comes with maven3 installed, or how they say "bundled".

How do i know this?
To check where ur maven is located and what executables ur ide is using u need to go to:
![[Pasted image 20240811134701.png]]
There we see "bundled".


if the Lifecycle from maven is not working that is probably because mvn is not set in the env vars.
First check it with mvn -v. 
Finding the bundled version required u to find where intellij is located and then copy path to plugins,maven,lib,maven3 folder:

Some defaults would look like:
![[Pasted image 20240811135028.png]]
For me it was: 
"C:\Disc\Dev\Tools\IntelliJ IDEA Community Edition\plugins\maven\lib\maven3"


THEN set the MAVEN_HOME env variable in System variables
THEN set the in the sys vars again add a new column with "%MAVEN_HOME%\bin"

NOTE: The mvn -v will require the JAVA_HOME to be set. check with java -v and echo %JAVA_HOME%
Find in intellij:
![[Pasted image 20240811135422.png]]

Now ur all set. You can run the lifecycle from within intellij
