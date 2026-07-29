figures_hires/ — full-resolution figure images (kept for when needed)
=======================================================================
All 31 paper figures as high-resolution PNG images, for viewing, slides,
posters, a project page, or any use that wants ready-made raster images:
  - 13 qualitative galleries: the original lossless PNG masters
    (2000-6600 px on the long edge)
  - 18 charts / schematics: rendered from their vector sources at 600 DPI

The vector (PDF) originals of the 18 charts are NOT lost — they remain in
../fig/figure/ and are what the LaTeX build uses. This folder is the
all-image convenience copy.

For a maximum-quality LaTeX rebuild (camera-ready)
--------------------------------------------------
  - Charts: keep using the vector PDFs already in ../fig/figure/ (sharper than
    any raster in print).
  - Galleries: copy the 13 gallery *.png here over ../fig/figure/ (they replace
    the submission's q95 *.jpg), then revert the gallery references in
    ../main.tex and ../sec/*.tex from `.jpg` back to `.png`, and recompile:
      pdflatex main && bibtex main && pdflatex main && pdflatex main
