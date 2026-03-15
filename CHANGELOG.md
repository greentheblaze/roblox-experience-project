# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- This CHANGELOG, to serve as the central area to document all changes made in full detail.
- "place-packages" directory for Wally so it can work in multiple directories simultaneously, and Rojo meta files inside them, primarily so Git has a reason to keep them, even if there are no packages being imported.
- New .gitignore globs for descendants of place-packages, except for meta files in them so Rojo always considers build folders.
- wally.toml files in package storage folders.
- A .styluaignore file with globs to prevent formatting imported packages.
- The Rojo default.project.json and otherplace.project.json files for use in deployment and [Roblox UI](https://github.com/filiptibell/roblox-ui).
- Roblox service directories inside src, and meta files to force Git to always see them.
- Support for Git submodules (through .gitmodules).

### Changed

- The name of `deploy_place.yaml` to `deploy-place.yaml` (from snake_case to kebab-case).
- Globs for the original unthought-out packages in .gitignore to the existing ones.
- Naming of "core" package storage folders to "internal" packages, to prevent confusion with Roblox's [`CorePackages`](https://robloxapi.github.io/ref/class/CorePackages.html).
- The original unthought-out package folder patterns in .gitattributes to the existing ones.
- The title of README.md and links to the repository to use the new project name: "roblox-experience-project" (it was previously "roblox-project").
- Various areas of this CHANGELOG to lower cognitive load when reading.

### Removed

- A [markdownlint](https://github.com/DavidAnson/markdownlint) disable directive from LICENSE file due to no longer using the extension.
- The `!.gitkeep` negation of the `/globalTypes.d.lua` ignore glob.
- The wally.toml file from the main directory due to Wally only being used in place-packages.
- Redundant `workflow_dispatch` and `schedule` configurations from ci.yaml.

### Fixed

- Build paths in otherplace.project.json so they aren't using the main place's directories.
- .gitignore so git submodules now appear (involved removing all globs to internal-packages after realizing that only git submodules will exist there).
- A violation of Keep a Changelog where adding a line to an existing file was documented. (A change that small shouldn't have been documented at all. It was also incorrectly documented as an addition, rather than a change to an existing file.)

[unreleased]: https://github.com/greentheblaze/roblox-experience-project/compare/9f2094d54cc151be75cf693fbf875bd6ab9ecf02...HEAD
