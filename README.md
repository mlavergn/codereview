# Code Review

Code Review Tools, Configurations, and Recommendations

## Linters

### Swift

- SwiftLint
  - https://github.com/realm/SwiftLint
  - Configuration: `.swiftlint.yml`
     - Setup options:
      - `ln -s swiftlint.yml .swiftlint.yml`
      - `mv swiftlint.yml .swiftlint.yml`

```bash
swiftlint --config .swiftlint.yml
```

### Objective-C

- oclint
  - https://github.com/oclint/oclinttl
  - Configuration: `.oclint`
     - Setup options:
      - `ln -s oclint.yml .oclint`
      - `mv oclint.yml .oclint`

```bash
xcodebuild -project MyProject.xcodeproj -scheme MyScheme -sdk macosx -configuration Debug build | xcpretty -r json-compilation-database -o compile_commands.json
oclint-json-compilation-database
oclint -rc CYCLOMATIC_COMPLEXITY=10 -rc LONG_CLASS=1000
```

## Formatters

### Swift

- swift-format
  - https://github.com/apple/swift-format
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
  - https://github.com/nicklockwood/SwiftFormat
  - Methodology
    - Text parser
    - Operates on line groups
    - Can ignore some text via configuration
  - Configuration: `.swiftformat` 
    - https://github.com/nicklockwood/SwiftFormat/blob/main/Rules.md
    - Setup options:
      - `ln -s swiftformat.cfg .swiftformat`
      - `mv swiftformat.cfg .swiftformat`

```bash
swiftformat **/*.swift
```

### Objective-C

- clang-format
  - https://clang.llvm.org/docs/ClangFormatStyleOptions.html
  - Standard with Xcode
  - Configuration: `.clang-format`
    - Setup options:
      - `ln -s clang-format.yml .clang-format`
      - `mv clang-format.yml .clang-format`

```bash
xcrun clang-format -i **/*.[hm]
```

## Style Guides

- Style guides based on Apple documentation and sample code
  - https://google.github.io/swift/

- Apple sample code:
  - https://developer.apple.com/documentation/swiftui/backyard-birds-sample