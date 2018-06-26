Copyright Wrapper for CNI Publications
======================================

This repository contains a LaTeX-wrapper for overlaying publications with a copyright notice and a reference to the conference/journal, where the document appeared.

The current version wraps the PDF-Version of a manuscript by appropriate textboxes.

## Background
Publishing a paper on the institute's website or in arXiv in most cases requires an appropriate copyright notice of the actual publisher, e.g. IEEE, ACM, or others, visibly overlayed on the first page of the uploaded document.

This repository provides a collection of such wrappers. (However, currently focused on arXiv and our institute homepage. This is done by the same wrapper.)

## Usage
* Make your adjustments in file ``Manuscript_arXiv.tex``.
	* Update filename of the manuscript
	* Update year
	* Set conference/journal if already accepted (leave blank otherwise)
	* Set DOI if already published (leave blank otherwise)
* Run ``pdflatex`` **twice** to see the results.

## Contact
Din't hesitate to contact Robert Falkenberg <robert.falkenberg@tu-dortmund.de> for further questions and support.