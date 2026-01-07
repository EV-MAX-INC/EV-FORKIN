# Revert Checklist

This document provides a checklist for reverting features or modules from the repository to ensure complete and consistent removals.

## Pre-Revert Analysis

- [ ] Identify all files added by the feature/module
- [ ] Identify all files modified by the feature/module
- [ ] Document the PR or commit that introduced the feature
- [ ] Create a list of all documentation references

## Code Removal

- [ ] Remove all source code files (e.g., Python, Java, JavaScript)
- [ ] Remove all configuration files specific to the feature
- [ ] Remove all test files for the feature
- [ ] Remove all example/demo files
- [ ] Remove all dependency declarations (requirements.txt, package.json, pom.xml, etc.)

## Documentation Updates

### README.md
- [ ] Remove from "Current Projects" section
- [ ] Remove feature-specific usage examples
- [ ] Remove feature-specific installation instructions
- [ ] Remove from project structure diagram
- [ ] Check that feature can remain in "Future Plans" if applicable

### CHANGELOG.md
- [ ] Remove feature entries from "Added" section (unless documenting the revert)
- [ ] Check that feature can remain in "Future Releases" if still planned
- [ ] Consider adding a "Removed" entry documenting the revert

### Other Documentation
- [ ] Review CONTRIBUTING.md for feature-specific examples (keep generic examples)
- [ ] Review IMPROVEMENTS.md (feature can remain in recommendations)
- [ ] Review DEPENDENCIES.md (remove if no longer planned, keep if future dependency)
- [ ] Review IP_COMPLIANCE.md (can remain for future reference)
- [ ] Check all other .md files for broken links or references

## Reference Validation

- [ ] Search for all mentions of feature name across all files
- [ ] Verify no broken links to removed files
- [ ] Ensure consistency between "current" and "planned" references
- [ ] Check that examples don't reference removed code

## Final Validation

- [ ] Run `git status` to verify no unintended changes
- [ ] Search for references: `grep -r 'FEATURE_NAME' --include='*.md' .` (replace FEATURE_NAME with actual feature, e.g., "perplSDK")
- [ ] Search for file references: `grep -r 'path/to/removed/file' --include='*.md' .` (replace with actual paths, e.g., "perplSDK/")
- [ ] Verify directory structure is clean: `find . -name 'FEATURE_DIR'` (replace FEATURE_DIR with actual directory, e.g., "perplSDK")
- [ ] Review git diff to confirm only intended changes
- [ ] Test any remaining examples or documentation references

## Communication

- [ ] Update PR description with comprehensive list of changes
- [ ] Document reason for revert (if not obvious)
- [ ] Tag any related issues
- [ ] Notify stakeholders if needed

## Post-Revert

- [ ] Monitor for any issues caused by the revert
- [ ] Update project board/issues as needed
- [ ] Consider creating a follow-up issue if feature will be reimplemented

---

## Notes

- **Current vs Planned**: Features can remain in "Future Plans" or "Planned Releases" sections even after code is reverted
- **Generic Examples**: Code examples in documentation like CONTRIBUTING.md can remain if they're generic/educational
- **Compliance Docs**: IP compliance and dependency documentation can remain for future reference
- **Be Surgical**: Only remove what was added, don't modify unrelated code
