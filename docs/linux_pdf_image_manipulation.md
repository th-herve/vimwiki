# Linux pdf image manipulation

## Compress pdf

```bash
convert -density 200x200 -quality 60 -compress jpeg input.pdf output.pdf
```
Adjust the parameters :
- density: pixel density in dpi, higher = better quality but bigger file
- quality: from 1 to 100, 100 = better quality/bigger file
- compress: compression algorithm

## Unite pdf

```bash
pdfunite file1.pdf file2.pdf file3.pdf ... output.pdf
```
