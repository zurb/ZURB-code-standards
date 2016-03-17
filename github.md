# GitHub

All GitHub repos need a readme (`README.md`), contributing document (`CONTRIBUTING.md`), and a license (`LICENSE`).

## Readme

For frameworks, the readme should be short, and mainly serve as a portal to other resources. The readme will have these sections:

- **Getting Started:** Links to various install methods. Always lead with the quickest install method, which for the frameworks is the CSS version.
- **Documentation:** Link to the documentation, and instructions on how to compile the documentation locally.
- **Contributing:** Link to contributing guide.

For libraries, the readme will contain installation and usage instructions. Larger libraries like Motion UI may have dedicated documentation folders, with pages written in Markdown.

## Issue Templates

The frameworks should have an issue template under `/.github/ISSUE_TEMPLATE.md` and a pull request template under `/.github/PULL_REQUEST_TEMPLATE.md`. The specific contents will vary between the three frameworks. The [issue template](https://github.com/zurb/foundation-sites/blob/develop/.github/ISSUE_TEMPLATE.md) and [pull request template](https://github.com/zurb/foundation-sites/blob/develop/.github/PULL_REQUEST_TEMPLATE.md) for Foundation for Sites provide a good model.

The issue template should:

- Recommend using the Foundation Forum for support requests.
- Ask the user to list the steps needed to reproduce the bug.
- Ask the user what they expected to happen, and what actually happened.
- Encourage the user to link to a CodePen or JSFiddle recreating the issue.

The pull request template should:

- Tell the user which branch to target (e.g., stable, development, old version).
- Encourage the user to write a unit/visual test showing the issue has been fixed.

## Contributing

The major frameworks should have a formal contributing document, which outlines how developers are brought on as team members, policies for submitting pull requests, and so on.

**Example:** [contributing.md on Foundation for Sites](https://github.com/zurb/foundation-sites/blob/develop/CONTRIBUTING.md)

Along with this, the major frameworks should also have a Code of Conduct. We have a custom one adapted from the Contributor Convenant.

**Example:** [code-of-conduct.md on Foundation for Sites](https://github.com/zurb/foundation-sites/blob/develop/code-of-conduct.md)

## License

All ZURB open source projects use the [MIT License](http://opensource.org/licenses/MIT).
