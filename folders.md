# Folder Structure

All three Foundation frameworks should use a similar folder structure.

- **dist:** Distribution files for the most stable version.
- **docs:** Documentation.
- **js:** JavaScript.
- **lib:** Any helper libraries needed to compile the documentation.
- **scss:** Sass.
- **test:** Unit tests.
  - **sass:** Sass unit tests
  - **js:** JavaScript unit tests
  - **visual:** Visual regression tests

These files are also common to every framework.

- **.editorconfig:** editorconfig file, which can be used by IDEs to format code a consistent way.
- **.gitignore:** Files to ignore in version control.
- **.npmignore:** Files to ignore when publishing an npm package.
- **bower.json:** Bower package definition.
- **composer.json:** Composer package definition.
- **package.js:** Meteor package definition.
- **package.json:** npm package definition.
- **.sass-lint.yml:** sass-lint config file.
- **.eslintrc:** ESLint config file.
