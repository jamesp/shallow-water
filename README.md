# shallow-water

[![CI](https://github.com/rse-standrewscs/shallow-water/workflows/CI/badge.svg)](https://github.com/rse-standrewscs/shallow-water/actions)
[![codecov](https://codecov.io/gh/rse-standrewscs/shallow-water/branch/master/graph/badge.svg)](https://codecov.io/gh/rse-standrewscs/shallow-water)
[![Dependabot Status](https://api.dependabot.com/badges/status?host=github&repo=rse-standrewscs/shallow-water)](https://dependabot.com)
[![](https://tokei.rs/b1/github/rse-standrewscs/shallow-water)](https://github.com/XAMPPRocky/tokei)

3D shallow water code by David Dritschel

[API documentation (master)](https://rse-standrewscs.github.io/shallow-water/shallow_water/index.html)

http://www-vortex.mcs.st-and.ac.uk/software.html

## Installing

In the root directory of the project:

```
cargo install --path .
shallow-water vstrip
shallow-water balinit
shallow-water swto3d
shallow-water nhswps
```

This will build and place a `shallow-water` binary in `~/.cargo/bin/` which, if in PATH, can then be used to run all 4 subcommands. It will use parameters found in `./parameters.toml` by default, an alternative parameter file path can be passed as an argument.

Final output is placed in the `2d` and `3d` folders, as well as in three `.asc` files.

### Using locally

`cargo run` can be used to run the program without installing.

```
cargo run --release -- -p parameters.yaml balinit
```

### Testing

To run all standard tests:

```
cargo test --release
```

To run the expensive (ignored by default) tests:

```
cargo test --release -- --ignored
```

If the `--release` flag is not set, the tests may take a long time to finish.

### Benchmarking

```
cargo bench
```
