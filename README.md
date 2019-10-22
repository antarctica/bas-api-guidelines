# BAS API Guidelines

## Status

This project is now obsolete and no longer maintained. This project is retained for reference and in case it's useful to others.

BAS Staff are recommended to follow the advice provided and maintained by the (UK) Government Digital Service (GDS), older versions of which were included in these guidelines.

Specifically refer to [API technical and data standards (v2 - 2019)](https://www.gov.uk/guidance/gds-api-technical-and-data-standards).

## Available formats

These guidelines are available in three formats

* Markdown - the definitive [1] and "working" file format in which all changes should be made [2]

* Microsoft Word - a release only format with suitable typesetting and layout for printing

* PDF - a release only format suitable for achieving, created from the Microsoft Word format

[1] Where differences exist between different formats, the markdown format is considered authoritative.

[2] The markdown format is available in two forms. The first is the full, complete guidelines, the second removes the contents of each guideline (and any other unreleased information).

## Creating alternate formats

### Microsoft word

1. Use [pandoc](https://pandoc.org) to covert the full guidelines from markdown to a Word File

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

1. From Microsoft Word version of the guidelines, export as a PDF

## License

© UK Research and Innovation (UKRI), 2014 - 2019, British Antarctic Survey.

You may use and re-use this software and associated documentation files free of charge in any format or medium, under
the terms of the Open Government Licence v3.0.

You may obtain a copy of the Open Government Licence at http://www.nationalarchives.gov.uk/doc/open-government-licence/
