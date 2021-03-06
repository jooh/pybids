# Changelog

## Version 0.7.0 (September, 2018)
This is a major, API-breaking release. It introduces a large number of new features, bug fixes, and improvements.

API-BREAKING CHANGES:
* A number of entities (or keywords) have been renamed to align more closely with the BIDS specification documents:
	* 'type' becomes 'suffix'
	* 'modality' becomes 'datatype'
	* 'acq' is removed (use 'acquisition')
	* 'mod' becomes 'modality'
* The following directories are no longer indexed by default: derivatives/, code/, stimuli/, models/, sourcedata/. They must be explicitly included using the 'include' initialization argument.
* The grabbids module has been renamed to layout and BIDSLayout.py and BIDSvalidator.py are now layout.py and validation.py, respectively.
* The BIDS validator is now enabled by default at layout initialization (i.e., `validate=True`)
* The `exclude` initialization argument has been removed.
* `BIDSLayout.parse_entities` utility has been removed (use the more flexible `parse_file_entities`).

NEW FEATURES:
* File metadata is now searchable (use `BIDSLayout.search_metadata()`)
* A new BIDSFile wrapper provides easy access to `.metadata` and `.image`
* HRF convolution is now supported via bundling of nistats' hemodynamic_models module; convolution is handled via the `convolve_HRF` transformation.

MINOR IMPROVEMENTS AND BUG FIXES:
* Specifying 'derivatives' in a paths specification now automatically includes 'bids' (#246)
* Variable loading via load_variables can now be done incrementally
* Expanded and improved path-building via `layout.build_path()`
* `get_collections` no longer breaks when `merge=True` and the list is empty (#202)
* Layout initialization no longer fails when `validate=True` (#222)
* The auto_contrasts field in the modeling tools now complies with the BIDS-Model spec (#234)
* Fix sum transformation
* Improved test coverage

## Version 0.6.5 (August 21, 2018)

* FIX: Do not drop rows of NaNs (#217) @adelavega
* FIX: Declare run as having integer type (#236) @effigies
* ENH: MEG support (#229) @jasmainak
* REF: rename grabbids to layout, closes #228 (#230) @ltirrell
* DOC: add .get_collection examples to tutorial (#219) @Shotgunosine
* DOC: Fix link in README to point to documentation (#223) @KirstieJane
* DOC: Add binder link for tutorial (#225) @KirstieJane
* MAINT: Restore "analysis" installation extra (#218) @yarikoptic
* MAINT: Do not import tests in \_\_init\_\_.py (#226) @tyarkoni

## Version 0.5.1 (March 9, 2018)
Hotfix release:

* Includes data files omitted from 0.5.0 release.
* Improves testing of installation.

## Version 0.5.0 (March 6, 2018)
This is a major release that introduces the following features:
* A new `bids.variables` module that adds the following submodules:
	* `bids.variables.entities.py`: Classes for representing BIDS hierarchies as a graph-like structure.
	* `bids.variables.variables.py`: Classes and functions for representing and manipulating non-imaging data read from BIDS projects (e.g., fMRI events, densely-sampled physiological measures, etc.).
	* `bids.variables.io.py`: Tools for loading variable data from BIDS projects.
	* `bids.variables.kollekshuns`: Containers that facilitate aggregation and manipulation of `Variable` classes.
* Extensions to the `BIDSLayout` class that make it easy to retrieve data/variables from the project (i.e., `Layout.get_collections`)
* A new `auto_model` utility that generates simple BIDS-Model specifications from BIDS projects (thanks to @Shotgunosine)
* A new `reports` module that generates methods sections from metadata in BIDS projects (thanks to @tsalo)
* Experimental support for copying/writing out files in a BIDS-compliant way
* Expand `bids.json` config file to include missing entity definitions
* Ability to parse files without updating the Layout index
* Updated grabbids module to reflect grabbit changes that now allow many-to-many mapping of configurations to folders
* Too many other minor improvements and bug fixes to list (when you're very lazy, even a small amount of work is too much)

## Version 0.4.2 (November 16, 2017)
We did some minor stuff, but we were drunk again and couldn't read our handwriting on the napkin the next morning.

## Version 0.4.1 (November 3, 2017)
We did some minor stuff, and we didn't think it was important enough to document.

## Version 0.4.0 (November 1, 2017)
We did some stuff, but other stuff was happening in the news, and we were too distracted to write things down.

## Version 0.3.0 (August 11, 2017)
We did some stuff, but we were drunk and forgot to write it down.

## Version 0.2.1 (June 8, 2017)
History as we know it begins here.
