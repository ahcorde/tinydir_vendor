
This document is a declaration of software quality for the `tinydir_vendor` package, based on the guidelines in [REP-2004](https://www.ros.org/reps/rep-2004.html).

# `tinydir_vendor` Quality Declaration

The package `tinydir_vendor` claims to be in the **Quality Level 1** category.

Below are the rationales, notes, and caveats for this claim, organized by each requirement listed in the [Package Requirements for Quality Level 1 in REP-2004](https://www.ros.org/reps/rep-2004.html).

## Version Policy

### Version Scheme

`tinydir_vendor` uses `semver` according to the recommendation for ROS Core packages in the [ROS 2 Developer Guide](https://index.ros.org/doc/ros2/Contributing/Developer-Guide/#versioning), and is at or above a stable version, i.e. `>= 1.0.0`.

### API Stability Within a Released ROS Distribution

TODO: Define policy to handle ABI stability for vendor packages

### ABI Stability Within a Released ROS Distribution

TODO: Define policy to handle ABI stability for vendor packages

### Public API Declaration

TODO: Define API for this package

## Change Control Process

`tinydir_vendor` follows the recommended guidelines for ROS Core packages in the [ROS 2 Developer Guide](https://index.ros.org/doc/ros2/Contributing/Developer-Guide/#change-control-process).

This includes:

- all changes occur through a pull request
- all pull request have two peer reviews
- all pull request must pass CI on all [tier 1 platforms](https://www.ros.org/reps/rep-2000.html#support-tiers)
- all pull request must resolve related documentation changes before merging

## Documentation

### Feature Documentation

TODO fix link. No documentation available, only some examples in the [README.md](https://github.com/cxong/tinydir/)

### Public API Documentation

TODO fix link

No documentation available

### License

The license for `tinydir_vendor` is Apache 2.0, and a summary is in each source file, the type is declared in the `package.xml` manifest file, and a full copy of the license is in the `LICENSE` file.

There is an automated test which runs a linter (ament_copyright) that ensures each file has a license statement.

### Copyright Statements

The copyright holders each provide a statement of copyright in each source code file in `tinydir_vendor`.

There is an automated test which runs a linter (ament_copyright) that ensures each file has at least one copyright statement.

## Testing

### Feature Testing

Each feature in `tinydir_vendor` has corresponding tests which simulate typical usage, and they are located in the [test folder](https://github.com/cxong/tinydir/tree/master/tests)  of the `tinydir` library.

### Public API Testing
TODO: Define API for this package ?

Each part of the public API have tests, and new additions or changes to the public API require tests before being added.
The tests aim to cover both typical usage and corner cases, but are quantified by contributing to code coverage.

### Coverage

TODO fix link, how to handle coverage for external dependencies?

No code coverage metric for this package

### Performance

TODO Will this package require performance testing?

### Linters and Static Analysis

`tinydir_vendor` uses and passes all the standard linters and static analysis tools for a vendored package as described in the [ROS 2 Developer Guide](https://index.ros.org/doc/ros2/Contributing/Developer-Guide/#linters-and-static-analysis). This includes using ament_lint_common to analyze the package manifest and its cmake files for correct syntax.

TODO any qualifications on what "passing" means for certain linters

## Dependencies

TODO: Finish analyzing the QD justifying Quality Level 1 for libyaml

`tinydir_vendor` depends directly on the external dependency `tinydir`, this one was qualified as quality level 1 as described thoroughly [QD tinydir](https://docs.google.com/document/d/18LiYAPO5_d7xuAfwpC7YLmbk8mO29aQf5iIC2hYL2XY/edit?usp=sharing).

## Platform Support

`tinydir_vendor` supports all of the tier 1 platforms as described in [REP-2000](https://www.ros.org/reps/rep-2000.html#support-tiers), and tests each change against all of them.

TODO make additional statements about non-tier 1 platforms?
