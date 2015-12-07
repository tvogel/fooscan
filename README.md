fooscan
=======
simple minded scanning daemon for Fujitsu ScanScnap S1300 and similar duplex passage scanners

This consists of three bash scripts:

- fooscan output.pdf

  duplex scans a stack of pages and saves it to output.pdf
  in-file customization: scan resolution (default 150 dpi) and crop rect (default A4, shifted 1.7 mm down-page)
  
- stripeven [-i] input.pdf

  drops all even pages from input.pdf and writes input_stripped.pdf
  
  -i: in-place: writes to input.pdf
  
- foodaemon

  checks scan button status every second; opens file-dialog for output PDF file; checks for overwrite;
  scans; displays scanned PDF; asks whether even pages shall be stripped;
  

Requirements
------------

- SANE scanimage with epjitsu driver (for button status)
- sane-backends >=1.0.25: contains fixes for image positioning when duplex-scanning with epjitsu
- ImageMagick convert for cropping and writing PDF
- pdftk for stripeven
- kdialog for foodaemon UI
- xdg-open for opening PDF

TODO
----

- ask for continuation after scanning for long documents

