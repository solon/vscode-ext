# OpenFGA Extension for VS Code

VS Code extension that provides syntax highlighting for the [OpenFGA](https://openfga.dev/) [language for authorization models](https://openfga.dev/docs/configuration-language).

[![Visual Studio Marketplace](https://img.shields.io/visual-studio-marketplace/v/openfga.openfga-vscode)](https://marketplace.visualstudio.com/items?itemName=openfga.openfga-vscode)
[![Open VSX Version](https://img.shields.io/open-vsx/v/OpenFGA/openfga-vscode)](https://open-vsx.org/extension/OpenFGA/openfga-vscode)
[![Release](https://img.shields.io/github/v/release/openfga/vscode-ext?sort=semver&color=green)](https://github.com/openfga/vscode-ext/releases)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://github.com/openfga/vscode-ext/blob/main/LICENSE)
[![Discord Server](https://img.shields.io/discord/759188666072825867?color=7289da&logo=discord "Discord Server")](https://discord.gg/8naAwJfWN6)
[![Twitter](https://img.shields.io/twitter/follow/openfga?color=%23179CF0&logo=twitter&style=flat-square "@openfga on Twitter")](https://twitter.com/openfga)

## About

[OpenFGA](https://openfga.dev) is an open source Fine-Grained Authorization solution inspired by [Google's Zanzibar paper](https://research.google/pubs/pub48190/). It was created by the FGA team at [Auth0](https://auth0.com) based on [Auth0 Fine-Grained Authorization (FGA)](https://fga.dev), available under [a permissive license (Apache-2)](https://github.com/openfga/rfcs/blob/main/LICENSE) and welcomes community contributions.

OpenFGA is designed to make it easy for application builders to model their permission layer, and to add and integrate fine-grained authorization into their applications. OpenFGA’s design is optimized for reliability and low latency at a high scale.

## Resources

- [OpenFGA Documentation](https://openfga.dev/docs)
- [OpenFGA API Documentation](https://openfga.dev/api/service)
- [Twitter](https://twitter.com/openfga)
- [OpenFGA Discord Community](https://discord.gg/8naAwJfWN6)
- [Zanzibar Academy](https://zanzibar.academy)
- [Google's Zanzibar Paper (2019)](https://research.google/pubs/pub48190/)

## Installation

You can install the OpenFGA VS Code plugin from:

- [OpenFGA on the VS Code marketplace](https://marketplace.visualstudio.com/items?itemName=openfga.openfga-vscode)
- [OpenFGA on the OpenVSX Registry](https://open-vsx.org/extension/OpenFGA/openfga-vscode)
- [The VSIX releases on GitHub](https://github.com/openfga/vscode-ext/releases) for manual installation

	![Installing from VSIX file](resources/vsix-install.png)

## Usage

The extension currently offers 3 core features, with more to come.

- Syntax Highlighting for OpenFGA files
- A unique theme for OpenFGA for VS Code
	- Once installed, go to your extensions
	- Click on `OpenFGA` and click `Set Color Scheme`
	- Click on `OpenFGA Dark` in the prompt

![Prompt to set OpenFGA Dark color scheme](resources/set-color-scheme.png)

- A command to transform `OpenFGA` files to `JSON`
	- Open an `OpenFGA` file in the editor 
	- Open the `Command Pallette` using Ctrl+Shift+P (Windows) or Command+Shift+P (OSX)
	- Select `OpenFGA: Transform DSL to JSON`
	- A new tab will open with the transformed code

![Prompt to execute OpenFGA: Transform DSL to JSON command](resources/transform-command-select.png)

## Development

- Run `npm install` in the root directory. This installs all necessary npm modules.
- Run `npm run compile && npm run test-node` to execute the client node test suite.

### Distribution (Optional)

To generate an installable build of this extension, you can do the following:

- Run `npm install --global @vscode/vsce` to get the latest version of `vsce` for packaging 
- Run `vsce package` to generate an installable `VISX` artifact for testing or distribution

### Structure

```
.
├── client // Language Client
│   ├── src
│   │   ├── test // End to End tests for Language Client / Server
│   │   ├── extension.node.ts // Language Client node entry point
│   │   └── extension.browser.ts // Language CLient web entry point
├── package.json // The extension manifest.
└── server // Language Server
    └── src
        ├── server.node.ts // Language Server node entry point
        ├── server.browser.ts // Language Server web entry point
        └── server.common.ts // Language Server common code
```

### Running the Client

- Run `npm install` in the root directory. This installs all necessary npm modules.
- Open the root directory in VS Code.
- Press Ctrl+Shift+B (Windows) or Command+Shift+B (OSX) to start compiling the client and server in [watch mode](https://code.visualstudio.com/docs/editor/tasks#:~:text=The%20first%20entry%20executes,the%20HelloWorld.js%20file.).
- Switch to the Run and Debug View in the Sidebar (Ctrl+Shift+D on Windows, Command+Shift+D on OSX).
- Select `Launch Client` from the drop down (if it is not already).
- Press ▷ to run the launch config (F5).

### Testing

- Run `npm install` in the root directory. This installs all necessary npm modules.
- Run `npm run compile` to compile the code & client for testing.
- Run `npm run test-node` to execute the client node test suite.

#### Remote Testing the Web functionality

- To manually test the extension in the browser for [VS Code for the Web](https://vscode.dev/) before publishing, follow [these instructions](https://code.visualstudio.com/api/extension-guides/web-extensions#test-your-web-extension-in-vscode.dev) to setup a VS Code for the Web instance with your local extension, and then proceed with the normal testing flow.

## Roadmap

A rough [roadmap](https://github.com/orgs/openfga/projects/3) for development priorities.

## Contributing

See [CONTRIBUTING](https://github.com/openfga/.github/blob/main/CONTRIBUTING.md).

## Author

[OpenFGA](https://github.com/openfga)

## License

This project is licensed under the Apache-2.0 license. See the [LICENSE](https://github.com/openfga/vscode-ext/blob/main/LICENSE) file for more info.
