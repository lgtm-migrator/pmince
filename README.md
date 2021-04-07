# MINCE

- **_MINCE Is Not Completely EMACS_**

## Overview

- **MINCE** is an Emacs-like text editor from **Mark of the Unicorn, Inc.**
- Originally available for **CP/M-80**, **CP/M-68K**, **PDP/RSX-11**, and
  **UNIX** systems

## Portable MINCE

- "**Portable MINCE**" is based on the last release of **MINCE** (_2.6_), plus:
  - **CP/M** system call translation
  - **8080/Z80** CPU emulation

## Building

- Required:

  - C compiler (`gcc`, `clang`, _etc_.)
  - GNU `make`
  - POSIX `cmp`, `env`, and `sh` (_Bourne_ _shell_)

- Optional:
  - Tcl `expect` and POSIX `sed`
    - Needed to override default terminal configuration (24 cols, 80 rows).

## Usage

- [Introduction](doc/prgintro.doc)
- [Command Summary](doc/scomm.doc)
- [Character Set](doc/ascii.txt)
- **MINCE** Manuals
  - [Getting Started](manual/MINCE_Install_Guide.pdf)
  - [User Guide](manual/MINCE_User_Guide.pdf)
  - [Addendum: Version 2.6](manual/MINCE_Addendum.pdf)
  - [Internal Documentation](manual/MINCE_Internal_Documentation.pdf)

## Tested configurations

- **ix86** (IA32)
  - **Debian** (Sid) 11, GNU C 10.2.0
  - **Haiku** (Walter) hrev55027, GNU C 2.95.3 (_20170720_)
- **x86**\_**64** (AMD64)
  - Solaris/**OpenIndiana** 20210407 (Hipster), SunOS/**illumos** 5.11, GNU C 3.4.3 (_20050802_)
  - **RHEL** 8.3, GNU C 8.4.1
  - **CentOS** 8 (Stream), GNU C 10.2.1
  - **Fedora** 33, GNU C 10.2.1
  - **Fedora** 33, Intel oneAPI DPC++ 2021.2.0 (_20210317_)
  - **Fedora** 34 Beta, AMD AOCC 2.3.0 (_20201110_)
  - **macOS** (Big Sur) 11.3 Beta 6, Xcode 12.4 (_1200.0.32.29_)
  - **OpenBSD** 6.8, Clang 10.0.1
- **ARMv7HF** (ARM32)
  - **Raspbian** (Buster) 10, GNU C 8.3.0 (_6+rpi1_)
- **ARM64** (AArch64)
  - **Debian** (Bullseye) 11, GNU C 10.2.1
  - **FreeBSD** 13.0-RC4, Clang 11.0.1 (_g43ff75f2c3fe_)
  - **FreeBSD** 13.0-RC5, GNU C 9.3.0
- **RISC-V** (RV64)
  - **Debian** (Sid) 11, GNU C 10.2.0

## Roadmap

- End-user configuration system, customizable via file or environment variables.
- Avoid main input busywait/spin-loop to reduce idle CPU usage.
- Translation of line-endings at run time (_use_ `dos2unix` _as_ _a_
  _workaround_).
- Translation of `PgUp` / `PgDn` / `Home` / `End` / cursor control / arrow keys.
- Build with GCC `-fno-common` and reduce `-Wall` warnings.
- Support crash recovery (by parsing `mince.swp`) in case of unclean exit.
- Add support for external filters, such as hexadecimal mode (via `xxd`).
- Support for automatic terminal resizing (_by catching and handling
  **SIGWINCH**_).
- Allow building **MINCE** binaries with various extensions; produce
  verified/tested configurations.
- Build and integrate **Scribble**, **Pencil**, and **Crayon**.
  - Automatic setup for **ANSI**/**ASME** _**Y14.1**_ (_US_) and _ISO_-_**216**_
    (_EU_) paper types.
  - End-user run time switching between different printer defintions.
  - Support for rendering (_NEC_, _Epson_, _Diablo_, etc.) proportional font
    printer output.
  - **Ghostscript** / **ImageMagick** for conversion of Crayon output to _PDF_,
    _PostScript_, etc.
  - Automate **Scribble** formatting to (_n_)_roff_ / _groff_, (_X_)_HTML_,
    _TeX_ / _LaTeX_, etc. (utilizing **Pandoc** or similar tools for
    conversion).
- Add Motorola **68000** CPU core, to support **MINCE-68K**.
  - Automatically invoke **MINCE-68K** version for large input files.
  - End-user configuration of default **MINCE** flavor (**MINCE-80** or
    **MINCE-68K**).
    - Native execution (_translation_) for **MINCE-68K** for **M68000** systems.
- User-configurable key bindings and remapping.
  - Allow user configuration _without_ requiring full recompilation.
  - Normalize key bindings and mappings between **MINCE** flavors.
- Support for **RSX-11**, (**Open**)**VMS**, **Windows**, and **OS/2** operating
  systems.

## Original Authors

- **Portable MINCE** contact:
  _[Jeffrey H. Johnson](https://github.com/johnsonjh/pmince)_
  \<[trnsz@pobox.com](mailto:trnsz@pobox.com)\>.
- **MINCE** _2.6_: Copyright © 1980-1982 by **Mark of the Unicorn, Inc.**
- **DIFF** _1.1_: Copyright © 1981 by **Mark of the Unicorn, Inc.**
- **Scribble**, **Pencil**, **Crayon** _1.3_: Copyright © 1981 by **Mark of the
  Unicorn, Inc.**
  - **MINCE** / **DIFF** / **Scribble** / **Pencil** / **Crayon**: Authored by
    _Jason_ _T._ _Linhart_, _Scott_ ("_Gyro_") _Layson_ _Burson_, _Craig_ _A._
    _Finseth_, _Brian_ _N._ _Hess_, and _Bill_ _Spitzak_.
- **CCOM80** (_Derived from **COM** 3.0_): Copyright © 1984-2008 by _Jim_
  _Cathey_, _Edmund_ _Ramm_, _Charlie_ _Gibbs_, and _Willi_ _Kusche_.
- **coffwrap** (_Derived from **bin2c**_): Copyright © 2015 by _Ondrej_ _Novak_.

## License

- See the [LICENSE](/LICENSE.md) file for important details.
