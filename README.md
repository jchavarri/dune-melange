# dune-bs

This is a development setup to explore and experiment around the integration of Dune with BuckleScript `bsc`
compilation tool.

For more context, see: https://github.com/ocaml/dune/issues/140.

## Setup

You need Esy, you can install the beta using [npm](https://npmjs.com):

```bash
npm install -g esy
```

> NOTE: Make sure `esy --version` returns at least `0.6.0` for this project to build.

Then run the `esy` command from this project root to install and build dependencies.

```bash
esy
```

## Getting started

To keep an incremental approach, the first thing that we're attempting to do is to build an `.ml` file written for
BuckleScript with Dune.

After running `esy` to download dependencies and build them, run 

```bash
esy step1
```

Which will attempt to build `bin/Hello.ml` with `dune` and `bsc` (still wip).

We will add more steps with more complex cases over time (with Reason syntax, with ppx, with libraries...).

## Local development flow

To develop locally, clone dune repository:

```bash
git clone https://github.com/jchavarri/dune
git checkout dune-bs
```

and add a resolution to this project `package.json` like:

```diff
  "resolutions": {
-   "@opam/dune": "jchavarri/dune:dune.opam#d29d5f4"
+   "@opam/dune": "link:../path/to/dune/dune.opam"
  }
```
