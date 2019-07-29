Copyright Overlays for Publications
======================================

This repository contains a LaTeX package to easily overlay preprints of your publications with a copyright notice and a reference to the conference/journal, where the document appeared/will appear. [Here is an Example](example-IEEE.pdf)

The package can be integrated directly into the manuscript's source or can be used as a wrapper for already generated PDF documents.

## Disclaimer
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## License
This package is released under MIT license.

## Background
Uploading a preprint of a paper on private websites, institute's websites or on arXiv in most cases requires an appropriate copyright notice of the actual publisher, e.g. [IEEE], [ACM], or others, which is visibly overlayed on the first page of the uploaded document.

This repository provides LaTeX toolbox to add such notes to a document.

## Usage
The copyright overlay can be used in two ways:

	1) Integrated into the manuscript's source
	2) Used as a wrapper to overlay an existing PDF with the text

### Integrate into the manuscript's source
Copy the following files into your manuscript's directory:

- ``copyright-overlay.sty``

together with any of the following templates you intend to use:

- ``ACM.def``
- ``IEEE.def``


Include the following definitions into your main ``.tex`` document and fill in your data.

```tex
% into the preamble
\usepackage[%
	IEEE,%
%	disabled,%	Don't show anything at all
	]{copyright-overlay}

\CopyrightAuthor{John Doe}
\CopyrightYear{2999}
\ConferenceName{Example Conference}
\Doi{123456/123456789}
\Bibtex{}

% on each page you wish to generate the overlay
\PrintCopyrightOverlay
```
Comment or clear the definitions, if their values are not known (yet), e.g. if the paper is accepted for presentation the DOI is not known. The text of the conference note will change appropriately.

The command ``\Bibtex{@inproceedings...}`` generates a PDF comment with the content of its argument in the upper right corner of the first page. This can be used to provide a BibTeX-Entry for your readers. However, special characters, line endings and tabs must be escaped properly:

```tex
\Bibtex{%
	@InProceedings\{MyBibtexKey2019a,\textCR\textLF
		\textHT{}Author = \{Max Mustermann\},\textCR\textLF
		\textHT{}Title = \{\{EXAMPLE\}: \{An\} example for a BIBTEX entry\},\textCR\textLF
		\textHT{}Booktitle = \{Ultimate Conference 2019\},\textCR\textLF
	\}
}
```

### Wrap an existing PDF
This package also provides an easy and ready-to-use wrapper to add overlays to PDF papers. Overlays are added on the first page only. However, the code can be easily adapted to achieve a different behaviour.

First, read the previous section to get familiar with the functionality and commands.

* Copy ``.sty`` and ``.def`` files into your working directory.
* Copy ``wrapper.tex`` as well.
* Make your adjustments in ``wrapper.tex``:
	* Update path/filename of your manuscript to wrap.
	* Check the year.
	* Set conference/journal if already accepted (leave blank otherwise).
	* Set DOI if already published (leave blank otherwise).
* Run ``pdflatex`` **twice** to see the results.

## FAQ

** All my references and URLs are surrounded by colored boxes. How to disable this? **

This wrapper uses the package ``hyperref`` in its default (or current) configurtion to create clickable references. To disable colored boxes, load ``hyperref`` package with option ``[hidelinks]`` before loading  ``copyright-overlay`` package:

```tex
\usepackage[hidelinks]{hyperref}
\usepackage[IEEE]{copyright-overlay}
```

## Contact
Don't hesitate to contact Robert Falkenberg <robert.falkenberg@tu-dortmund.de> for further questions and support.

## References

[IEEE]: https://www.ieee.org/content/dam/ieee-org/ieee/web/org/pubs/author_version_faq.pdf
[ACM]: https://www.acm.org/publications/policies/copyright-policy