# Erpe.**Analyzers**

**Erpe.Analyzers** is a NuGet metapackage designed for use in my personal projects. This package bundles essential code analysis tools and enforces strict code quality, style, and security standards to maintain consistency across all of my repositories.

## Included Analyzers

The following analyzers are bundled in **Erpe.Analyzers**:

- **[Microsoft.VisualStudio.Threading.Analyzers](https://github.com/microsoft/vs-threading/blob/master/doc/analyzers/index.md)**: Helps enforce best practices for asynchronous programming and threading, reducing the risk of deadlocks and improving app performance.
- **[SecurityCodeScan.VS2019](https://security-code-scan.github.io/)**: Scans code for common security vulnerabilities to help detect security issues early.
- **[SonarAnalyzer.CSharp](https://github.com/SonarSource/sonar-dotnet)**: Provides a range of analyzers for code quality and reliability based on SonarQube rules.
- **[StyleCop.Analyzers](https://github.com/DotNetAnalyzers/StyleCopAnalyzers)**: Ensures consistent style and formatting across the codebase following the StyleCop ruleset.

## Key Configuration Settings

In addition to bundling analyzers, **Erpe.Analyzers** enforces the following configurations in consuming projects:

- **Nullable Reference Types**: Enabled for all projects to promote null-safe code.
- **Analysis Level**: Set to `latest-all`, which applies the latest .NET analyzer rules.
- **Treat Warnings as Errors**: Helps to catch issues early in the development process.
- **Enforce Code Style in Build**: Ensures that all code style rules are enforced as part of the build process.

## Style and Code Configuration

**Erpe.Analyzers** also includes additional files to maintain consistency across all personal projects:

- **`stylecop.json`**: Configures StyleCop settings, including setting the company name used in header comments to "Frank Hambach".

- **`Erpe.Analyzers.globalconfig`**: Contains configuration to disable certain warnings globally:
    - **SA0001**: Projects are not required to produce an XML documentation file during the build.
    - **SA1600**: Allows undocumented code elements.

## Installation

To install **Erpe.Analyzers**, add the following package source to your `nuget.config` file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <packageSources>
    <add key="GitHub" value="https://nuget.pkg.github.com/frankhambach/index.json" />
  </packageSources>
</configuration>
```

Then, add **Erpe.Analyzers** to your project by running:

```shell
dotnet add package Erpe.Analyzers
```

## Usage

Once installed, the analyzers and settings provided by **Erpe.Analyzers** will automatically be applied to your project. You don’t need additional configuration to enable these rules; they’re configured to enforce consistent code quality across all projects.

## License

This project is licensed under the [MIT License](https://opensource.org/license/mit).

## Contributions

This project is intended for personal use, so contributions are not actively accepted. However, feel free to fork it if you’d like to make custom modifications for your own use.