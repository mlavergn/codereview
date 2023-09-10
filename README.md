# Code Review

Code Review Tools, Configurations, and Recommendations

## Linters

### Swift

- SwiftLint
  - https://github.com/realm/SwiftLint
  - Configuration: `.swiftlint.yml`
```bash
swiftlint --config .swiftlint.yml
```

### Objective-C

- oclint
  - https://github.com/oclint/oclinttl
  - Configuration: `.oclint`
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
```bash
swiftformat MyProject/**/*.swift
```

- SwiftFormat
  - https://github.com/nicklockwood/SwiftFormat
  - Methodology
    - Text parser
    - Operates on line groups
    - Can ignore some text via configuration
  - Configuration: `.swiftformat` https://github.com/nicklockwood/SwiftFormat/blob/main/Rules.md
```bash
swiftformat MyProject/**/*.swift
```

### Objective-C

- clang-format
  - https://clang.llvm.org/docs/ClangFormatStyleOptions.html
  - Standard with Xcode
  - Configuration: `.clang-format`
```
xcrun clang-format -i MyProject/**/*.[hm]
```

## Style Guides

- Style guides based on Apple documentation and sample code
  - https://google.github.io/swift/
