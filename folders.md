# Folder Structure

All three Foundation frameworks should use a similar folder structure.

- **.github:** Container for issue and pull request templates.
- **_build:** Temporary folder that holds compiled assets.
- **dist:** Distribution files for the most recent stable version.
- **docs:** Documentation.
- **js/ts:** JavaScript (or TypeScript).
- **lib:** Any helper libraries needed to compile the documentation.
- **scss:** Sass.
- **test:** Unit tests.
  - **sass:** Sass unit tests
  - **javascript:** JavaScript unit tests
  - **visual:** Visual regression tests

These files are also common to every framework.

- **.editorconfig:** editorconfig file, which can be used by IDEs to format code a consistent way.
- **.eslintrc:** ESLint config file.
- **.gitignore:** Files to ignore in version control.
- **.npmignore:** Files to ignore when publishing an npm package.
- **.sass-lint.yml:** sass-lint config file.
- **.travis.yml:** Travis config file.
- **bower.json:** Bower package definition.
- **composer.json:** Composer package definition.
- **CONTRIBUTING.md:** Contributing guidelines.
- **LICENSE:** MIT License.
- **package.js:** Meteor package definition.
- **package.json:** npm package definition.
- **README.md:** Framework readme.
