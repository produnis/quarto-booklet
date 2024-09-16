# quarto-booklet

A Quarto extension to create a PDF booklet from a single `.qmd` file.

This extension provides structured page numbering, making it ideal for booklets with distinct sections. The page numbering works as follows:
- **Title page:** No page numbers
- **Frontmatter:** Roman numerals (starting with i)
- **Mainmatter:** Arabic numerals (starting with 1)


## Cover Picture
The default cover image included in this repository is from [Pixabay](https://pixabay.com/de/photos/flohmarkt-b%C3%BCcher-kiste-st%C3%B6bern-237460/).

To use a custom cover picture, specify the filename in the `YAML` header like this:

```yaml
cover: my-new-file.jpg

```



## Headings
Headings are printed in blue by default. This is controlled by the `in-header.tex` file. To revert the headings to black, comment out the following lines in `in-header.tex`:

```
%\addtokomafont{chapter}{\color{HSNRblue1}}
%\addtokomafont{section}{\color{HSNRblue1}}
%\addtokomafont{subsection}{\color{HSNRblue2}}
%\addtokomafont{subsubsection}{\color{HSNRblue2}}
%\addtokomafont{paragraph}{\color{HSNRblue2}}
```

## LaTeX packages
If you require specific LaTeX packages, you can add them directly in the `in-header.tex` file.


## Title page
To modify the style of the title page, edit the `before-body.tex` file. This allows full customization of the title page layout in LaTeX.

## Table of Contents, List of Figures, and List of Tables
To ensure the correct page numbering with both Roman and Arabic numerals, the table of contents (TOC), list of tables (LOT), and list of figures (LOF) have been manually integrated into the extension. As a result, these lists are controlled by custom `YAML` parameters:

- **mytoc:** For the table of contents
- **mylof:** For the list of figures
- **mylot:** For the list of tables

The default value is `true`, so all three lists are included. You can control their inclusion by setting these parameters to `false` in the YAML header.


## Page numbering
Page numbering is set up in  `before-body.tex` and follows this structure:

- **Title page:** No page numbers
- **Frontmatter:** Roman numerals (starting with i)
- **Mainmatter:** Arabic numerals (starting with 1)

