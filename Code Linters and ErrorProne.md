#### Linters for Java - Google Style Guide

###### Preconditions
**MUST:** ideally i want linter that i can bind to both the hotkey and pre-push hook. So that no non formatted files are in the code base.

**WISH:** In the best case scenario i can configure the linter, so that we can better the formating:

```Java
If(variableName = null) {
	throw NullPointerException("variable was null")
}
// becomes
If(variableName = null)
	throw NullPointerException("variable was null")
// OR
If(variableName = null) throw NullPointerException("variable was null")
```
OR
customising of unit test names and //AAA or //GWT patterns in tests.
##### Linters 
https://dev.to/ketiko/enforcing-java-coding-styles-1a9
1. google-java-format: [link](https://android.googlesource.com/platform/external/google-java-format/+/4e83b17484ff59cd2efac15da02f0b02d79b571d)
	- Directly from google - https://github.com/google/google-java-format
	- formats with the default CTRL+ALT+L, replaces the Intellij hotkey
	- ~~**prone to errors, because the hotkey can be forgotten to be executed**
	- ~~**no idea if i can make it to run on a git hook**
	- ~~**does not show where the problems are, if any**
	- proektite se poddurjat
	- https://github.com/Cosium/git-code-format-maven-plugin pravi commit hook
	- https://mvnrepository.com/artifact/com.cosium.code/google-java-format/5.3
	- https://mvnrepository.com/artifact/com.google.googlejavaformat/google-java-format/1.23.0
	- https://stackoverflow.com/questions/50857698/how-to-format-code-according-to-google-java-format
2. Checkstyle
	https://checkstyle.org/writingchecks.html
	- extendable !!!!!! but needs attention time to extend ofc