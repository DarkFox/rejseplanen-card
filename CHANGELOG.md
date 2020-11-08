# Changelog

## [1.5.3]
### Fixed
- CSS fix (#8) by @DurgNomis-drol

## [1.5.0]
### Added
- Added `show_scheduled_time` option to show the scheduled departure time, instead of a countdown.

### Other
- Removed parenthesis around track.
- Updated Readme with configuration options table and correct HACS install process.

## [1.4.0]
### Added
- Track number, if available (HA 0.115 and above only).
- Shows real time departure time, if delayed (HA 0.115 and above only).

### Other
- Updated some NPM packages.
- Added hacs.json file.

## [1.3.0]
### Added
- Option to limit number of shown departures using `max_entries`.
- This changelog.

### Fixed
- The card would crash the entire view, if the entity did not exist. Now shows a nice warning instead.
