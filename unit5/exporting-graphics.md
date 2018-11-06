---
title: Exporting graphics
layout: default
---

# Exporting Graphics


## Graphics systems in computers

Computers use two different graphical systems to create images.

### 1. [vector graphics](https://en.wikipedia.org/wiki/Vector_graphics) use points, lines, curves and polygons, thus images are infinitely scalable, e.g. pdf, svg, eps.
   + Type: graphs, diagrams.
   + Use: Most journals.
   + Recommended: .pdf, .eps
   
### 2. [raster graphics](https://en.wikipedia.org/wiki/Raster_graphics) or bitmaps use a rectangular grid of pixels, e.g. bmp, png, jpg.
   + Type: photos, images, maps.
   + Use: graphs in websites, embedded figures in word processors, photos in manuscripts.
   + Recommended: .png

Graphics in R can be saved as any of these formats. 

Most journals require graphs to be saved in a vector format such as .pdf. This kind of graphic is scalable, ie you can zoom in and it will still look crisp.


## How to export graphics from R

There are various options depending on your operating system and way of working with R.

### 1. RStudio

OS: all

Within the 'plot' sub-window, click 'Export' to select how to save the plot.


### 2. graphics functions: pdf(), png(), tiff(), jpeg(), ...

OS: all

Once you have the figure looking as you like it, the best way to produce publication-quality figures is to use a specific graphics device function. For graphs, the best format is usually pdf().

Specify the file name and its size. The pdf is sized in inches (7 x 7); png and jpg in pixels (480 x 480). Once you have run all the plotting you want, close the graphics device with dev.off(). The file with then appear in your folder.

```r
pdf("filename.pdf", height = 7, width = 7, ... )

plot( ... )

dev.off()
```

## 3. copy and paste

OS: windows, (mac?)

To import a graph from R into a word processor such as Microsoft Word, right-click on the graph in R, and copy and paste as normal.


### 4. save from the graphics window

OS: windows, (mac?)

From the open graphics windown, right-click as above, and save as a Windows metafile, bitmap or postscript file.


## Importing graphics to manuscripts and presentations

Many word processing packages struggle with importing pdf files, and so png files are easier to work with.

If you do your writing in Markdown or LaTeX, pdf are easy to work with.

