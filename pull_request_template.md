name: Code Review Item Template
about: Format a code review item
title: "[Item]: "
body:
  - type: markdown
    attributes:
      value: |
        Please complete this code review item template
  - type: checkboxes
      id: comment-type
      attributes:
        label: Comment type
        description: This comment aligns with our [Code of Conduct](https://example.com)
        options:
          - label: New concern
          - label: Reoccurrence of earlier concern
          - label: Kudos
      validations:
        required: true        
  - type: textarea
    id: what-change
    attributes:
      label: What should be changed?
      description: Specify what should be changed
      placeholder: We should change ...
      value: ""
    validations:
      required: true
  - type: textarea
    id: why-change
    attributes:
      label: Why should it be changed?
      description: Justify why it should be changed
      placeholder: This is need because ...
      value: ""
    validations:
      required: true
  - type: dropdown
    id: concern-level
    attributes:
      label: Level of concern
      description: What is the appropriate level of concern for this comment?
      options:
        - Nice to Have
        - Important
        - Expected
        - Blocking
      default: 0
    validations:
      required: true
  - type: dropdown
    id: concern-type
    attributes:
      label: Type of concern
      description: What is the appropriate type of concern for this comment?
      options:
        - Style
        - Typo
        - Documentation
        - Test Coverage
        - Documentation
        - Performance
        - Resource Leak
        - Security
        - Regression
      default: 0
    validations:
      required: true
