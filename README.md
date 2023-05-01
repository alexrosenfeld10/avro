# Apache Avro™

[![test c][test c img]][test c]
[![test c#][test c# img]][test c#]
[![test c++][test c++ img]][test c++]
[![test java][test java img]][test java]
[![test javascript][test javascript img]][test javascript]
[![test perl][test perl img]][test perl]
[![test ruby][test ruby img]][test ruby]
[![test python][test python img]][test python]
[![test php][test php img]][test php]

[![rust continuous integration][rust continuous integration img]][rust continuous integration]
[![rust clippy check][rust clippy check img]][rust clippy check]
[![rust security audit][rust security audit img]][rust security audit]

[![codeql c#][codeql c# img]][codeql c#]
[![codeql java][codeql java img]][codeql java]
[![codeql javascript][codeql javascript img]][codeql javascript]
[![codeql python][codeql python img]][codeql python]

-----

Apache Avro™ is a data serialization system.

Learn more about Avro, please visit our website at:

  https://avro.apache.org/

# About this version 
- support multiple schemas files
- allow reference to types on external schema file

## To test it:

### Build project Avro.codegen. 
This project generate the dotnet tool, it was renaming as *avrogenms* (instead of avrogen) to avoid conflict wth original Apache tool.
When buil, a nuget package with *avrogenms* tool will be generated.
Package version is read from file "share\VERSION.txt", currently set to "1.10.1-ms"

### Install avrogenms tool
You can install this tool globally or locally, I prefere to do it locally. 

To install the tool:
- open command prompt on "Avro.sampleMultiSchema" folder (you can do it on any folder but just keep it as root folder for all other steps)
- run command: 

Local install (on folder "Avro.sampleMultiSchema\tool"):

`> dotnet tool install --tool-path .\tool --add-source ..\..\..\..\lang\csharp\src\apache\codegen\bin\Debug\ Apache.Avro.Tools --version 1.10.1-ms
`

Global install:

`> dotnet tool install --global --add-source ..\..\..\..\lang\csharp\src\apache\codegen\bin\Debug\ Apache.Avro.Tools --version 1.10.1-ms
`

you should have message as:

`
You can invoke the tool using the following command: avrogenms.
Tool 'apache.avro.tools' (version '1.10.1-ms') was successfully installed.
`

The project Avro.sampleMultiSchema contains 2 schema files that are used to test. To generate C# classes from these files just build project Avro.sampleMultiSchema. Or run the tool from command line as follow:

`
Avro.sampleMultiSchema>.\tool\avrogenms -ms .\avroFiles\schema01.avsc;.\avroFiles\schema02.avsc .\generated
`

If you build the project, the build should pass including the 2 generated C# classes from schema files.
If you exectue the tool from command line, the 2 c# classes are generated at folder "Avro.sampleMultiSchema\generated"

*schema01.avsc* generates class *generated\org\vehicule.cs* which contains the field *model* of type *CarModel* which is declared on class *generated\com\cars\CarModel.cs* generated from *schema.02.avsc*.

<!-- Arranged this way for easy copy-pasting and editor string manipulation -->

[test c]:          https://github.com/apache/avro/actions/workflows/test-lang-c.yml
[test c#]:         https://github.com/apache/avro/actions/workflows/test-lang-csharp.yml
[test c++]:        https://github.com/apache/avro/actions/workflows/test-lang-c++.yml
[test java]:       https://github.com/apache/avro/actions/workflows/test-lang-java.yml
[test javascript]: https://github.com/apache/avro/actions/workflows/test-lang-js.yml
[test perl]:       https://github.com/apache/avro/actions/workflows/test-lang-perl.yml
[test ruby]:       https://github.com/apache/avro/actions/workflows/test-lang-ruby.yml
[test python]:     https://github.com/apache/avro/actions/workflows/test-lang-py.yml
[test php]:        https://github.com/apache/avro/actions/workflows/test-lang-php.yml

[rust continuous integration]: https://github.com/apache/avro/actions/workflows/test-lang-rust-ci.yml
[rust clippy check]:           https://github.com/apache/avro/actions/workflows/test-lang-rust-clippy.yml
[rust security audit]:         https://github.com/apache/avro/actions/workflows/test-lang-rust-audit.yml

[codeql c#]:         https://github.com/apache/avro/actions/workflows/codeql-csharp-analysis.yml
[codeql java]:       https://github.com/apache/avro/actions/workflows/codeql-java-analysis.yml
[codeql javascript]: https://github.com/apache/avro/actions/workflows/codeql-js-analysis.yml
[codeql python]:     https://github.com/apache/avro/actions/workflows/codeql-py-analysis.yml

[test c img]:          https://github.com/apache/avro/actions/workflows/test-lang-c.yml/badge.svg
[test c# img]:         https://github.com/apache/avro/actions/workflows/test-lang-csharp.yml/badge.svg
[test c++ img]:        https://github.com/apache/avro/actions/workflows/test-lang-c++.yml/badge.svg
[test java img]:       https://github.com/apache/avro/actions/workflows/test-lang-java.yml/badge.svg
[test javascript img]: https://github.com/apache/avro/actions/workflows/test-lang-js.yml/badge.svg
[test perl img]:       https://github.com/apache/avro/actions/workflows/test-lang-perl.yml/badge.svg
[test ruby img]:       https://github.com/apache/avro/actions/workflows/test-lang-ruby.yml/badge.svg
[test python img]:     https://github.com/apache/avro/actions/workflows/test-lang-py.yml/badge.svg
[test php img]:        https://github.com/apache/avro/actions/workflows/test-lang-php.yml/badge.svg

[rust continuous integration img]: https://github.com/apache/avro/actions/workflows/test-lang-rust-ci.yml/badge.svg
[rust clippy check img]:           https://github.com/apache/avro/actions/workflows/test-lang-rust-clippy.yml/badge.svg
[rust security audit img]:         https://github.com/apache/avro/actions/workflows/test-lang-rust-audit.yml/badge.svg

[codeql c# img]:         https://github.com/apache/avro/actions/workflows/codeql-csharp-analysis.yml/badge.svg
[codeql java img]:       https://github.com/apache/avro/actions/workflows/codeql-java-analysis.yml/badge.svg
[codeql javascript img]: https://github.com/apache/avro/actions/workflows/codeql-js-analysis.yml/badge.svg
[codeql python img]:     https://github.com/apache/avro/actions/workflows/codeql-py-analysis.yml/badge.svg
