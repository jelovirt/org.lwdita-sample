# Schema Configuration Sample Project

A sample project how to configure a [custom schema](https://github.com/jelovirt/org.lwdita/wiki/Markdown-Schema)
for [LwDITA plug-in](https://github.com/jelovirt/org.lwdita) for DITA-OT.

## Requirements

* Java 11 or newer

[Authenticate to GitHub Packages](https://docs.github.com/en/packages/learn-github-packages/introduction-to-github-packages#authenticating-to-github-packages)
and configure the personal access token (PAT) to `gradle.properties`:

```properties
gpr.user=<USERNAME>
gpr.key=<TOKEN>
```

Where `<USERNAME>` is your GitHub username and `<TOKEN>` is the personal access token.

## Customization Example

To customize the sample project files to create your own customization.

1. Edit `settings.gradle` and change the project name `com.acme` to match the new customization ID `com.company`.
   ```groovy
   rootProject.name = 'com.company'
   ```
2. Move `src/main/java/com/acme/AcmeSchemaProvider.java` to `src/main/java/com/company/WikiSchemaProvider.java`.
3. Edit the Java file and rename the class from `AcmeSchemaProvider` to match the new class name and update the package
   to match the new package.
   ```java
   package com.company;
   …
   public class WikiSchemaProvider implements SchemaProvider {
   …
   ```
4. Edit `src/main/resources/META-INF/services/com.elovirta.dita.markdown.SchemaProvider` and update the class name and
   package.
   ```
   com.company.WikiSchemaProvider
   ```
5. Edit `src/main/java/com/company/WikiSchemaProvider.java` and change which Markdown parser extensions are used and
   change the options.

## Building

1. Build plug-in distribution

   ```shell
   ./gradlew dist
   ```
   Plug-in distribution is created in `build/distributions/com.acme-1.0.0.zip`.
