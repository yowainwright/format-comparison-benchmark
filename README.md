# Rome vs Prettier Format Comparison Benchmark

The npm scripts within this repository's `package.json` can be used to compare Rome Format vs Prettier. Initial notes written 04/06/2022. The scripts were written to be run on Mac. Specifically, a M1 Mac Pro was used.

> I'm excited about [Rome tools](https://rome.tools/) and [Rust](https://www.rust-lang.org/) 🦀 so I decided to do my own experiment after [this post](https://rome.tools/blog/2022/04/05/rome-formatter-release)!

---

## Scripts

- **`test:prettier:js`**: Run prettier on all JavaScript files added to a temp directory.
- **`test:rome:js`**: Run rome format on all JavaScript files added to temp directory.
- **`test:prettier:all`**: Run prettier on all CSS, JSON, JavaScript, Markdown in a temp directory.
- **`test:rome:feature-parity`**: Run rome format, markdownlint, jsonlint, and stylelint on all CSS, JSON, JavaScript, Markdown in a temp directory.

### Script Anatomy

Each script creates a temp directory (`/dump`), copies config files and [rambda](https://www.npmjs.com/package/ramda) from `node_modules` to run prettier and rome format. Tiems are measured using [gnomon](https://www.npmjs.com/package/gnomon).👌

---

## Benchmarks

Local Benchmarks

| Script | Rome | Prettier |
| :---: | :---: | :---: |
| js only | 1.5404s | 2.0353s |
| all | *2.2669s | 2.7163s |

\*I think I've written the script `test:rome:feature-parity` so that stylelint & markdownlint basically don't run. Will review. 🧐


---

## Projects Code Is Copied From For Convenience

- **[kerns](https://raw.githubusercontent.com/kerns/dummy/master/README.md)**: a dummy toolkit
- **[jsonplaceholder](https://jsonplaceholder.typicode.com/)** a json placeholder toolkit
- **[Simple CSS](https://simplecss.org/)**: a no-css-class css framework
