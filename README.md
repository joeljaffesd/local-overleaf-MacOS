# Overleaf Toolkit

This repository contains the Overleaf Toolkit, the standard tools for running a local
instance of [Overleaf](https://overleaf.com). This toolkit will help you to set up and administer both Overleaf Community Edition (free to use, and community supported), and Overleaf Server Pro (commercial, with professional support).

The [Developer wiki](https://github.com/overleaf/overleaf/wiki) contains further documentation on releases, features and other configuration elements.


## Getting Started

Clone this repository locally:

``` sh
git clone https://github.com/overleaf/toolkit.git ./overleaf-toolkit
```

Then follow the [Quick Start Guide](./doc/quick-start-guide.md).


## Troubleshooting

### Font Compilation Errors

If you encounter LaTeX compilation errors related to missing fonts or packages, such as:

```
Font T1/ptm/m/n/10=ptmr8t at 10.0pt not loadable: Metric (TFM) file not found.
LaTeX Error: File `listings.sty' not found.
LaTeX Error: File `caption.sty' not found.
LaTeX Error: File `subfig.sty' not found.
```

This indicates that essential font packages or LaTeX packages are missing from your TeX Live installation. To resolve this:

1. **Quick Fix (Temporary)**: Install fonts and packages in the running container:
   ```sh
   ./bin/install-packages
   ```

2. **For persistent setup**: Run the font installation script after each container restart, or include it in your deployment process.

The script installs:
- URW Base 35 fonts (Times, Helvetica, Courier, etc.)
- TeX Gyre fonts (modern alternatives)
- Common LaTeX packages (listings, xcolor, geometry, amsmath, caption, subcaption, subfig, float, booktabs, etc.)
- Proper font mapping updates

**Note**: Package installations in containers are not persistent and will need to be re-run if you recreate your containers.


## Documentation

See [Documentation Index](./doc/README.md)


## Contributing

See the [CONTRIBUTING](https://github.com/overleaf/overleaf/blob/main/CONTRIBUTING.md) file.


## Getting Help

Users of the free Community Edition should [open an issue on github](https://github.com/overleaf/toolkit/issues). 

Users of Server Pro should contact `support@overleaf.com` for assistance.

In both cases, it is a good idea to include the output of the `bin/doctor` script in your message.

