Copyright © 2011 Ejwa Software. All rights reserved.

This program comes with ABSOLUTELY NO WARRANTY.
This is free software, and you are welcome to redistribute it under
certain conditions; see the accompanying license.txt and license-lgpl.txt
files for further details.

For questions regarding maven-gitdep-plugin you can contact the current
maintainer in charge at maven-gitdep-plugin@ejwa.se.

usage:

in pom file you would list dependency like this:

        <dependency>
			<groupId>jr9999</groupId>
			<artifactId>github_module1</artifactId>
			<version>1.0-SNAPSHOT</version>
		</dependency>

build plugin entry like this:

            <plugin>
				<groupId>com.ejwa</groupId>
				<artifactId>maven-gitdep-plugin</artifactId>
				<version>0.1</version>
				<configuration>
					<gitDependencies>
						<gitDependency>
							<groupId>jr9999</groupId>
							<artifactId>github_module1</artifactId>
							<location>https://github.com/jr9999/github_module1.git</location>
							<branch>master</branch>
							<version>1.0-SNAPSHOT</version>
							<reinstall>true</reinstall>
						</gitDependency>
					</gitDependencies>
				</configuration>
				<executions>
					<execution>
						<id>clean-gitdep-exec</id>
						<phase>clean</phase>
						<goals>
							<goal>cleanup</goal>
						</goals>
					</execution>
					<execution>
						<id>compile-gitdep-exec</id>
						<phase>compile</phase>
						<goals>
							<goal>prepare</goal>
							<goal>download</goal>
							<goal>install</goal>
						</goals>
					</execution>
				</executions>
			</plugin>


all goals:

    install, cleanup, download, prepare
