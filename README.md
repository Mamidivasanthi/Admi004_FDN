Its a Spring boot project where we are generating POJO Classes using XML SCHEMA DEFINITION[XSD].We should use JAXB plugin for automating the code generation.
Here is the plugin and dependencies that need to be used :
<dependency>
			<groupId>jakarta.xml.bind</groupId>
			<artifactId>jakarta.xml.bind-api</artifactId>
			<version>2.3.3</version>
		</dependency>

<dependency>
			<groupId>javax.activation</groupId>
			<artifactId>javax.activation-api</artifactId>
			<version>1.2.0</version>
		</dependency>

  <plugin>
				<groupId>org.codehaus.mojo</groupId>
				<artifactId>jaxb2-maven-plugin</artifactId>
				<version>2.5.0</version>
				<executions>
					<execution>
						<goals>
							<goal>xjc</goal>
						</goals>
					</execution>
				</executions>
				<configuration>
					<sources>
						<source>src/main/resources/admin004.xsd</source>
					</sources>
					<outputDirectory>${project.build.directory}/generated-sources/</outputDirectory>
					<externalEntityProcessing>true</externalEntityProcessing>
				</configuration>
				<dependencies>
					<!-- Add JAXB dependencies -->
					<dependency>
						<groupId>javax.xml.bind</groupId>
						<artifactId>jaxb-api</artifactId>
						<version>2.3.1</version>
					</dependency>
					<dependency>
						<groupId>org.glassfish.jaxb</groupId>
						<artifactId>jaxb-runtime</artifactId>
						<version>2.3.1</version>
					</dependency>
				</dependencies>
			</plugin>

  
