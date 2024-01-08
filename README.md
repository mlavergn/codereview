# Code Review

Code Review Tools, Configurations, and Recommendations

## Linters

### Swift Linters

- SwiftLint
  - [https://github.com/realm/SwiftLint](https://github.com/realm/SwiftLint)
  - Configuration: `.swiftlint.yml`
    - Setup options:
      - `ln -s swiftlint.yml .swiftlint.yml`
      - `mv swiftlint.yml .swiftlint.yml`

```bash
swiftlint --config .swiftlint.yml
```

### Objective-C Linters

- oclint
  - [https://github.com/oclint/oclint](https://github.com/oclint/oclinttl)
  - Configuration: `.oclint`
    - Setup options:
      - `ln -s oclint.yml .oclint`
      - `mv oclint.yml .oclint`

```bash
xcodebuild -project MyProject.xcodeproj -scheme MyScheme -sdk macosx -configuration Debug build | xcpretty -r json-compilation-database -o compile_commands.json
oclint-json-compilation-database
oclint -rc CYCLOMATIC_COMPLEXITY=10 -rc LONG_CLASS=1000
```

> OCLint requires a "JSON compilation database" files to perform it's linting. This file contains a list of the Xcode build plan with the compiler flags that Xcode will pass to the compiler for each file. This complicates using oclint since we have to first run a `build` pass on the project, post-process the output using `xcpretty`, then post-process the `xcpretty` output using the `oclint-json-compilation-database` tool.

- [https://github.com/xcpretty/xcpretty](https://github.com/xcpretty/xcpretty)

```bash
gem install xcpretty
```

## Formatters

### Swift Formatters

- swift-format
  - [https://github.com/apple/swift-format](https://github.com/apple/swift-format)
  - Methodology
    - Parses code into AST then outputs AST through pretty printing
    - Strips all custom formatting
    - Can modify output formatting via configuration
  - Configuration: `.swift-format.json`
    - Setup options:
      - `ln -s swift-format.json .swift-format.json`
      - `mv swift-format.json .swift-format.json`

```bash
swiftformat **/*.swift
```

- SwiftFormat
  - [https://github.com/nicklockwood/SwiftFormat](https://github.com/nicklockwood/SwiftFormat)
  - Methodology
    - Text parser
    - Operates on line groups
    - Can ignore some text via configuration
  - Configuration: `.swiftformat`
    - [Rules](https://github.com/nicklockwood/SwiftFormat/blob/main/Rules.md)
    - Setup options:
      - `ln -s swiftformat.cfg .swiftformat`
      - `mv swiftformat.cfg .swiftformat`

```bash
swiftformat **/*.swift
```

### Objective-C Formatters

- clang-format
  - [https://clang.llvm.org/docs/ClangFormatStyleOptions.html](https://clang.llvm.org/docs/ClangFormatStyleOptions.html)
  - Standard with Xcode
  - Configuration: `.clang-format`
    - Setup options:
      - `ln -s clang-format.yml .clang-format`
      - `mv clang-format.yml .clang-format`

```bash
xcrun clang-format -i **/*.[hm]
```

## Style Guides

- Apple sample code:
  - [Apple Swift Style Sample](https://developer.apple.com/documentation/swiftui/backyard-birds-sample)
- Style guides based on Apple documentation and sample code
  - [Google Swift Style Guide](https://google.github.io/swift/)
