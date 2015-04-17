# Maven assembly plugin output file messy code problem

When we use Maven <artifactId>maven-assembly-plugin</artifactId> plugin, cause the comments in the XML files output chinese messy code,I try to change the pom.xml config encoding to UTF-8,but is invalid:
```
<plugin>
	<artifactId>maven-compiler-plugin</artifactId>
	<version>2.4</version>
	<configuration>
		<source>1.6</source>
		<target>1.6</target>
		<encoding>UTF-8</encoding>
	</configuration>
</plugin>
<plugin>
	<groupId>org.apache.maven.plugins</groupId>
	<artifactId>maven-resources-plugin</artifactId>
	<version>2.4</version>
	<configuration>
		<encoding>UTF-8</encoding>
	</configuration>
</plugin>
```
finally,problem solved through change MAVEN_OPTS args:

* MAVEN_OPTS = -Dfile.encoding=UTF-8