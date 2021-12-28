# Changelog

All notable changes to this project will be documented in this file. The format
is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and the
project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.4.0] - 2021-12-28

### Added
- Package translations for Debian 7.

### Fixed
- Improve aliases `gcc-full` and `pyenv-dev` for Debian 4 and Debian 8.
- Improve cleanup of packages after installations with `pmm-install`.

## [0.3.0] - 2021-10-29

### Added
- Package translations for Debian 6.0.

### Changed
- Remove system `xz-utils` as `pyenv-dev` dependency and instead compile
  `xz-utils` from source when compiling Python 3.3+.
- Remove system `libsqlite3-dev` as `pyenv-dev` dependency and instead compile
  SQLite from source.

### Removed
- Remove `tk-dev` and `xz-utils` for `pyenv-dev` in Debian-like systems.

## [0.2.0] - 2021-09-10

### Added
- Support to specify ucs2/ucs4 (unicode variant) in Python installation.
- Access to Linux kernel header version through `pmm-system`.
- Possiblity to enable/disable `CAN` definitions in system `socket.h`.
- Save Python build log inside the Python installation folder.
- Support to get system Perl version.

### Changed
- Rename main executables from `manager` to `pmm`.
- Move `poorman-manager` files to `bin` folder.
- Move OS information from command `pmm-info` to `pmm-system`.
- Modify handling of Python patches during installation so that it will be
  easier to append custom patches to those provided by PyEnv.
- Change default package manager in Debian 4.0 from `apt-get` to `aptitude` if
  `aptitude` is found in the system.
- Enforce OpenSSL 1.0.2 in Python versions that expect OpenSSL 1.1.1 when the
  system Perl version is too old to compile OpenSSL 1.1.1.
- Remove system `libffi-dev` as `pyenv-dev` dependency and instead compile
  `ffi` from source when compiling Python 3.6+.

### Fixed
- Check `pip` version before using `--no-cache-dir` (elder versions do not have
  this option).
- Fix Python `_decimal` not being built for Python 3.3+ when using too old GCC.
- Fix Python `_gdbm` and `_dbm` not being built for Python.
- Fix Python `ossaudiodev` not being built for Python 2.6 and Python 3.1.
- Fix Python `linuxaudiodev` not being built for Python 2.6.
- Fix Python modules not being built for Python 3.2 (`ossaudiodev` for 3.2.0
  and 3.2.1, `_posixsubprocess` for 3.2.3, `_sqlite3` for 3.2.4).

## [0.1.0] - 2021-08-02

### Added
- Initial version of `poorman-manager`.
- Basic commands to get OS information (e.g. package manager, distribution
  name and version).
- Basic features to handle package management (clean, install, remove, update).
- Custom installation of OpenSSL 1.0.2 and 1.1.1, and possibility to enable
  (and later disable) into `/usr/local/ssl`.
- Custom installation of Python 2.6+ and 3.1+ by means of PyEnv and other
  required preparation steps.
- Automatic cleanup of Python installed environments right after installation
  (e.g. byte-compiled files, test scripts).
- Helper scripts to install Python packages through `pip` if available.


[Unreleased]:
https://github.com/molinav/poorman-manager/compare/v0.4.0...master
[0.4.0]:
https://github.com/molinav/poorman-manager/compare/v0.3.0...v0.4.0
[0.3.0]:
https://github.com/molinav/poorman-manager/compare/v0.2.0...v0.3.0
[0.2.0]:
https://github.com/molinav/poorman-manager/compare/v0.1.0...v0.2.0
[0.1.0]:
https://github.com/molinav/poorman-manager/releases/tag/v0.1.0
