# BAS API Guidelines

## Current version

The latest published version of these guidelines can be found in the **master** branch. Versions are tagged using semantic versioning.

The latest pre-publication version of these guidelines (which contains pending corrections, additions or other changes) can be found in the **develop** branch.

## Release process

1. When significant changes have been made, or a significant period of time has past, the develop branch will be forked into a new **release** branch.

2. The release branch will be discussed to ensure agreement of any changes.

3. Proofing and other pre-publication steps will then be performed to produce a release ready set of changes. This includes the creation of Microsoft Word and PDF versions of the updated guidelines.

3. The release branch is merged into the **master** branch and tagged as the next version of the guidelines.

4. The newly tagged version becomes the latest version of the guidelines.

## Available formats

These guidelines are available in three formats

* Markdown - the definitive [1] and "working" file format in which all changes should be made [2]

* Microsoft Word - a release only format with suitable typesetting and layout for printing

* PDF - a release only format suitable for achieving, created from the Microsoft Word format

[1] Where differences exist between different formats, the markdown format is considered authoritative.

[2] The markdown format is available in two forms. The first is the full, complete guidelines, the second removes the contents of each guideline (and any unreleased information).

## Creating alternate formats

### Microsoft word

1. Use [pandoc]() to covert the full guidelines from markdown to a Word File

2. Open file in word (2013) and covert to latest file format, save

3. Change the document theme to the word default styles

4. Adjust headings as follows:

    * Title:

    	  * Space after: `20`

	* Heading 1:

		* Space after: `15`

	* Heading 2:

		* Space before: `24`

		* Space after: `10` 

		* Set font weight to `normal` (i.e. not bold)

	* Intense quote:

		* Align: `left`

		* Font size: `12`

5. Adjust all headings in document up one level (previous heading 1 becomes title)

6. Set 'introduction' sections (version, authors, status) to `subheading` style

7. Set all block-quotes (size 10 text) to `intense quote` style

8. Set page breaks:

	* After 'introduction' sections (version, authors, status)

	* Before 'Aims and objectives' section

	* Each section after and including "General principles" must have a page break

	* Where a paragraph hangs (split paragraph)

	* To even out pages within a section

9. Add table of contents after 'introduction' sections (version, authors, status)

10. Set document meta-data:

	* Title: `BASIS API Guidelines`

	* Status: `Version: x.x.x` (replace `x.x.x` with release version)

11. Add page numbers to page footer (plain, right aligned)

12. Add document meta-data to page header (Title \N Status)

13. Set font-colour of 'status' in header to sub-title font colour

### PDF

1. From Microsoft Word version of guidelines export as an 'Adobe PDF' (if Acrobat Pro installed), otherwise as a 'PDF'.