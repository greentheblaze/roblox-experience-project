# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- This CHANGELOG, to serve as the central area to document all changes made in full detail.
- New .gitignore globs for place package storage folders' descendant files, except for all meta files in them so Rojo can consider the folders always, but leaves Wally in charge of installing packages during builds (regardless of whether or not any packages are actually in them).
- "place-packages" directory for Wally so it can work in multiple directories simultaneously, and Rojo meta files inside them, primarily so Git has a reason to keep them, even if there are no packages being imported.
- Wally configuration (wally.toml) files in package storage folders.
- An empty line to aftman.toml (formatter).
- .styluaignore file with globs to ignore formatting all imported packages.
- The Rojo project.json files (default.project.json and otherplace.project.json).
- Roblox service folders for places and meta files inside them that explicitly define their Roblox `ClassName` properties, additionally forcing Git to not ignore them if they don't have any children (same as packages).
- Support for Git submodules through .gitmodules.

### Changed

- The name of `deploy_place.yaml` to `deploy-place.yaml` (from snake_case to kebab-case) for readability.
- The original unthought-out package folder patterns in .gitignore to the existing ones.
- "Core" package storage folders to "Internal" packages to prevent confusion with Roblox's [`CorePackages`](https://robloxapi.github.io/ref/class/CorePackages.html).
- The original unthought-out package folder patterns in .gitattributes to the existing ones.
- The title of README.md and links to the repository to use the new project name: "roblox-experience-project" (it was previously "roblox-project").

### Removed

- A [markdownlint](https://github.com/DavidAnson/markdownlint) disable directive from LICENSE file due to removing the use of the extension.
- The `!.gitkeep` negation of the `/globalTypes.d.lua` ignore glob.
- wally.toml file from the main directory due to Wally only being used in the place-packages directory.

### Fixed

- Build paths in otherplace.project.json so they aren't using those that should be exclusive to the default place.
- .gitignore so git submodules now appear (involved removing all globs to internal-packages after realizing that only git submodules will exist there).

[unreleased]: https://github.com/greentheblaze/roblox-experience-project/compare/9f2094d54cc151be75cf693fbf875bd6ab9ecf02...HEAD
