Copyright Wrapper for CNI Publications
======================================

This repository contains a LaTeX-Wrapper for overlaying publications with a copyright notice and a reference to the conference/journal, where the document appeared.

The current version wraps the PDF-Version of a manuscript by appropriate textboxes.

## Background
Publishing a paper on the institute's website or in arXiv in most cases requires an appropriate copyright notice of the actual publisher, i.e., IEEE, ACM, visibly overlayed in the uploaded document.

This repository provides a collection of such wrappers. (However, currently focused on arXiv and our institute homepage, which is the same wrapper.)

## Usage
* Make your adjustments in file ``Manuscript_arXiv.tex``.
	* Update filename of the manuscript
	* Update year
	* Set conference/journeal if already accepted (leave blank otherwise)
	* Set DOI if already published (leave blank otherwise)
* Run ``pdflatex`` to see the results.

## Contact
Contact Robert Falkenberg <robert.falkenberg@tu-dortmund.de> for further questions and support.