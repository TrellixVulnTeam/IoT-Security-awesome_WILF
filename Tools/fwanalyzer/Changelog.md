# Change Log

## Unreleased

### Added
- NEW _cpiofs_ for cpio as filesystem
- NEW universal _check.py_ (so you just need to write a custom unpacker)
- NEW _android/unpack.sh_ (for _check.py_)
- better options for scripts (FileContent and DataExtract)

### Fixed
- $PATH in makefile
- FileContent file iterator
- _squashfs_ username parsing

## [v1.2.0] - 2019-11-19

### Changed
- moved to go 1.13
- only store _current_file_treepath_ if filetree changed

## [v.1.1.0] - 2019-10-15

### Added
- NEW FileCmp check for full file diff against 'old' version
- allow multiple matches for regex based DataExtract

### Fixed
- squashfs username parsing

## [v.1.0.1] - 2019-09-19

### Fixed
- filename for BadFiles check output

## [v.1.0.0] - 2019-08-15

### Added
- CI
- Build instructions

## [initial] - 2019-08-05
