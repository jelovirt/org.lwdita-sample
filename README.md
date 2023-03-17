# Schema Configuration Sample Project

A sample project how to configure a [custom schema](https://github.com/jelovirt/org.lwdita/wiki/Markdown-Schema) for [LwDITA plug-in](https://github.com/jelovirt/org.lwdita) for DITA-OT.

## Requirements

* Java 11 or newer

[Authenticate to GitHub Packages](https://docs.github.com/en/packages/learn-github-packages/introduction-to-github-packages#authenticating-to-github-packages)
and configure the personal access token (PAT) to `gradle.properties`:

```properties
gpr.user=<USERNAME>
gpr.key=<TOKEN>
```

Where `<USERNAME>` is your GitHub username and `<TOKEN>` is the personal access token.

## Building

1. Build plug-in distribution

   ```shell
   ./gradlew dist
   ```
   Plug-in distribution is created in `build/distributions/org.lwdita.example-1.0.0.zip`.
