# SFCL poster and paper

Landing page for the poster QR code.

- `index.html` - the page GitHub Pages serves
- `poster.pdf` - the poster, School of Engineering A1 template layout. Do not
  rename this one either: the page links to this exact filename and the printed
  QR code can no longer be changed.
- `paper.pdf` - the submitted report WITHOUT its Declaration of Originality
  Form: that form is a scanned image carrying a handwritten signature, and
  this page is public, so the public copy starts at the title page (48 pp
  of the submitted 50). Rebuild it by dropping pages 1-2 of the submitted
  PDF. Do not rename it: the poster QR resolves to this page and the
  printed code cannot be changed.

Both links carry a `?v=<date>` cache buster. GitHub Pages serves these files with
`Cache-Control: max-age=600`, so bump the date in `index.html` whenever a PDF is
replaced - otherwise a phone that has already opened one keeps showing its cached
copy. Bump the stamp, never the filename.
