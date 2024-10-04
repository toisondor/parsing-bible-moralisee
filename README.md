# Parsing the *Bible Moralisée*, by Jesse D. Hurlbut
*Image coordinates for subdividing source images of La Bible Moralisée on Gallica.bnf.fr*


The *Bible Moralisée* is a medieval manuscript tradition that illustrates each episode of the Bible along with accompanying moralized interpretations. 

A detailed description of these works is presented by John Lowden in his two-volume study on the *Making of the Bibles Moralisées* (Penn State University Press, 2000). According to Lowden, only seven copies of this work survive today. So far, only two manuscripts are included in this repository. These are the latest copies and are both found in the Bibliothèque Nationale de France: manuscripts [Fr. 167](https://gallica.bnf.fr/ark:/12148/btv1b8447300c/), dating from the end of the fourteenth century, and [Fr. 166](https://gallica.bnf.fr/ark:/12148/btv1b105325870/), which dates to the beginning of the fifteenth century. Lowden provides a detailed examination of each of these manuscripts in his first volume, pages 221-250 and 251-284 respectively.

These two manuscripts were selected for inclusion in this corpus of data because (1) they represent the end of the tradition; (2) because of the direct relationship of the earlier manuscript serving as the model for the later; (3) because Fr. 167 is the longest and most complete representation of the Bible of any of the other *Bibles Moralisées*; (4) because of the accessibility of the images via IIIF API. Note that the two manuscripts collate extremely closely, but that Fr. 166 is incomplete and stops in the middle of the Book of Isaiah.

The images for these manuscripts are all maintained and served directly from the resources of the Bibliothèque Nationale de France (BNF) as made available through [Gallica](https://gallica.bnf.fr/). The data in this repository parses out the structured contents of each page (illustrations and captions) as cropped selections. The coordinates for these selections can be integrated with the API of the International Image Interoperability Framework (IIIF) which these institutions have generously adopted. 

Permission for the re-use of these images can be granted only under the terms of Gallica and the BNF. The JSON data included here is made available by Jesse D. Hurlbut under a Creative Commons license, but any project that consults this resource or its underlying data should acknowledge the use of this collection.

**Creative Commons License**

Parsing the *Bible Moralisée* by Jesse D. Hurlbut is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/). 

![Creative Commons License buttons](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)

## Project Description
Here are two sample pages of the *Bible Moralisée*. They illustrate the regular layout and structure of each page. 

![Two pages of Manuscript Fr 166, folios 4v and 5r](https://github.com/toisondor/assets/blob/main/BNF-fr166-4v-5r-small.jpeg)

Both manuscripts are organized in the following way. Each page is divided into four sections or quadrants. Each quadrant contains two illustrations—the first of which depicts a scene from the Bible (ABCD); the second depicts the interpretation of that scene (abcd). All illustrations have descriptive captions written in both Latin and Middle French.

![Schematic of the page divided into four groups, each containing two illustrations with their captions](https://github.com/toisondor/assets/blob/main/icon-page.png)

Those studying the *Bible Moralisée* may prefer to study each pair of images together or separately. Some may be more interested in the textual captions, while others may focus on the illustrations alone. For this reason, the JSON data include coordinates for seven different selections within each quadrant, as described below.  

## Corpus Scope
The JSON data provided here contains the coordinates for cropping the digital images housed on Gallica.bnf.fr.

- Manuscript Fr. 167 contains 2562 pairs of illustrations. Each pair is cropped in seven different ways, for a total set of coordinates for 17,934 images.

- Manuscript Fr. 166, which includes only the Old Testament through a portion of Isaiah, contains 1352 pairs of illustrations. Seven sets of coordinates for each pair yields 9,464 images.

The total number of images in the combined corpus is 27,398.

## Value of the Corpus
The corpus includes illustrations for every episode of the Bible. There are exegetical interpretations for each one of these episodes. Text and illustration provide juxtaposed and sometimes differing views on each element. The textual captions appear in both Latin and Middle French, providing interesting footholds for linguistic analysis. Two different copies of the *Bible Moralisée* which were created 30 or 40 years apart provide differentiating views and variation between them that is worth studying.  

## Using the Data
The API for accessing cropped images from Gallica.bnf.fr is comprised of key elements as seen in this example:
```
https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/f30/746,3052,1817,2301/pct:70/0/native.jpg
```
- The manuscript is identified by the 'btv' access number

    - Manuscript Fr. 167 is btv1b8447300c
    - Manuscript Fr. 166 is btv1b105325870

- The page or "view" number is indicated by the "f" access number (not the same as the folio number).

- The four numbers separated by commas are the coordinates for the x, y, width, and height of the image selection.

## Format of the Data
The JSON data for these two manuscripts do not constitute IIIF-compliant manifests but can be used in conjunction with those manifests (found here: [Mansucript Fr. 167](https://gallica.bnf.fr/iiif/ark:/12148/btv1b8447300c/manifest.json) and [Mansucript Fr. 166](https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/manifest.json)).

### group[]
The main body of image coordinates is organized under the array "group" --Note that group[0] includes a summary of the contents for each of the other groups. A group contains all the selection coordinates for one quadrant of a given page.
```
"group":
[
{"template":["f-number", "folio", "collation", "quadrant(A-D)", "selection(1-7)", "x", "y", "width", "height"]},
{"sel":[
    {"coord":[15,"1r",1,"A",1,334,673,1860,2332]},
    {"coord":[15,"1r",1,"A",2,110,673,2084,1192]},
    {"coord":[15,"1r",1,"A",3,350,1804,1838,1185]},
    {"coord":[15,"1r",1,"A",4,62,348,1327,1400]},
    {"coord":[15,"1r",1,"A",5,1270,668,923,1208]},
    {"coord":[15,"1r",1,"A",6,344,1815,1013,1159]},
    {"coord":[15,"1r",1,"A",7,1250,1799,947,1207]}]},
{"sel":[
    {"coord":[15,"1r",2,"B",1,378,2988,1833,2365]},
    {"coord":[15,"1r",2,"B",2,378,2988,1833,1185]},
    {"coord":[15,"1r",2,"B",3,378,4117,1833,1220]},
    {"coord":[15,"1r",2,"B",4,378,2957,1004,1195]},
    {"coord":[15,"1r",2,"B",5,1284,3008,921,1175]},
    {"coord":[15,"1r",2,"B",6,387,4117,1004,1268]},
    {"coord":[15,"1r",2,"B",7,1257,4117,1001,1236]}]}, 
```
Within each "coord" array, one finds:
- the "f" access number
- the folio number
- the collation number (which collates the scenes between the two Bibles, e.g., the creation of Adam has the same collation number in both manuscripts)
- the quadrant on each page (ABCD). Each quadrant contains two illustrations with captions.
- the selection number: each quadrant has coordinates for seven different image selections which are as follows:

1. Duplex: both illustrations with captions
 
 ![Duplex](https://github.com/toisondor/assets/blob/main/icon-Duplex.png)
 
2. Simplex Top: The top illustration with its caption
 
 ![Simplex Top](https://github.com/toisondor/assets/blob/main/icon-Simplex-top.png)
 
3. Simplex Bottom: The bottom illustration with its caption
 
 ![Simplex Bottom](https://github.com/toisondor/assets/blob/main/icon-Simplex-bottom.png)
 
4. Text Top: The caption (in Latin and French) of the top illustration
 
 ![Text Top](https://github.com/toisondor/assets/blob/main/icon-Text-top.png)
 
5. Image Top: The illustration at the top of the quadrant
 
 ![Image Top](https://github.com/toisondor/assets/blob/main/icon-Image-top.png)
 
6. Text Bottom: The caption (in Latin and French) of the bottom illustration
 
 ![Text Bottom](https://github.com/toisondor/assets/blob/main/icon-Text-bottom.png)
 
7. Image Bottom: The illustration at the bottom of the quadrant
 
 ![Image Bottom](https://github.com/toisondor/assets/blob/main/icon-Image-bottom.png)
 
- the coordinate for x
- the coordinate for y
- the coordinate for width
- the coordinate for height

### bible[]
The "bible" array contains the first and last collation numbers that correspond to each book of the Bible. For example, Genesis is found in collations 1-136; Exodus, in collations 137-223, etc.

## Examples
An active demonstration of the use of this data for the side-by-side comparison of the two manuscripts can be seen at [https://jessehurlbut.net/2bibles/](https://jessehurlbut.net/2bibles/#).

### Example 1. The first Duplex selection in the Book of Exodus from manuscript Fr. 167
Having retrieved the group that includes collation 137 (the beginning of Exodus) from Part1_BNF-Fr167.json, we can use the data in selection 1 to create a link to retrieve the Duplex image.
```
{"sel":[
    {"coord":[43,"18r",137,"A",1,174,865,1812,2252]},
    {"coord":[43,"18r",137,"A",2,78,865,1892,1144]},
    {"coord":[43,"18r",137,"A",3,78,1932,1902,1185]},
    {"coord":[43,"18r",137,"A",4,62,748,1119,1176]},
    {"coord":[43,"18r",137,"A",5,1094,876,875,1144]},
    {"coord":[43,"18r",137,"A",6,72,1943,1141,1095]},
    {"coord":[43,"18r",137,"A",7,1106,1927,883,1191]}]},
```

Selection 1: [https://gallica.bnf.fr/iiif/ark:/12148/btv1b8447300c/f43/174,865,1812,2252/pct:70/0/native.jpg](https://gallica.bnf.fr/iiif/ark:/12148/btv1b8447300c/f43/174,865,1812,2252/pct:70/0/native.jpg)


### Example 2. Parse out all the illustrations (without captions) of folio 1r of manuscript Fr. 166
Having retrieved the four groups that appear on folio 1r from Part2_BNF-Fr166.json, we extract the coordinates for selections 5 (top image of each group) and 7 (bottom image of each group) to create a series of links to retrieve the eight images.
```
{"sel":[
    {"coord":[15,"1r",1,"A",1,334,673,1860,2332]},
    {"coord":[15,"1r",1,"A",2,110,673,2084,1192]},
    {"coord":[15,"1r",1,"A",3,350,1804,1838,1185]},
    {"coord":[15,"1r",1,"A",4,62,348,1327,1400]},
    {"coord":[15,"1r",1,"A",5,1270,668,923,1208]},
    {"coord":[15,"1r",1,"A",6,344,1815,1013,1159]},
    {"coord":[15,"1r",1,"A",7,1250,1799,947,1207]}]},
{"sel":[
    {"coord":[15,"1r",2,"B",1,378,2988,1833,2365]},
    {"coord":[15,"1r",2,"B",2,378,2988,1833,1185]},
    {"coord":[15,"1r",2,"B",3,378,4117,1833,1220]},
    {"coord":[15,"1r",2,"B",4,378,2957,1004,1195]},
    {"coord":[15,"1r",2,"B",5,1284,3008,921,1175]},
    {"coord":[15,"1r",2,"B",6,387,4117,1004,1268]},
    {"coord":[15,"1r",2,"B",7,1257,4117,1001,1236]}]},
{"sel":[
    {"coord":[15,"1r",3,"C",1,2098,682,1737,2334]},
    {"coord":[15,"1r",3,"C",2,2098,682,1737,1200]},
    {"coord":[15,"1r",3,"C",3,2098,1812,1737,1185]},
    {"coord":[15,"1r",3,"C",4,2098,672,917,1009]},
    {"coord":[15,"1r",3,"C",5,2909,698,916,1175]},
    {"coord":[15,"1r",3,"C",6,2103,1797,932,1180]},
    {"coord":[15,"1r",3,"C",7,2903,1797,937,1196]}]},
{"sel":[
    {"coord":[15,"1r",4,"D",1,2111,2963,1756,2355]},
    {"coord":[15,"1r",4,"D",2,2111,2979,1756,1175]},
    {"coord":[15,"1r",4,"D",3,2095,4083,1772,1246]},
    {"coord":[15,"1r",4,"D",4,2111,2974,957,1185]},
    {"coord":[15,"1r",4,"D",5,2946,2974,921,1185]},
    {"coord":[15,"1r",4,"D",6,2094,4094,968,1043]},
    {"coord":[15,"1r",4,"D",7,2966,4078,881,1235]}]},
```

Quadrant A, selection 5: [https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/f15/1270,668,923,1208/pct:70/0/native.jpg](https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/f15/1270,668,923,1208/pct:70/0/native.jpg)

Quadrant A, selection 7: [https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/f15/1250,1799,947,1207/pct:70/0/native.jpg](https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/f15/1250,1799,947,1207/pct:70/0/native.jpg)

Quadrant B, selection 5: [https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/f15/1284,3008,921,1175/pct:70/0/native.jpg](https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/f15/1284,3008,921,1175/pct:70/0/native.jpg)

Quadrant B, selection 7: [https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/f15/1257,4117,1001,1236/pct:70/0/native.jpg](https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/f15/1257,4117,1001,1236/pct:70/0/native.jpg)

Quadrant C, selection 5: [https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/f15/2909,698,916,1175/pct:70/0/native.jpg](https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/f15/2909,698,916,1175/pct:70/0/native.jpg)

Quadrant C, selection 7: [https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/f15/2903,1797,937,1196/pct:70/0/native.jpg](https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/f15/2903,1797,937,1196/pct:70/0/native.jpg)

Quadrant D, selection 5: [https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/f15/2946,2974,921,1185/pct:70/0/native.jpg](https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/f15/2946,2974,921,1185/pct:70/0/native.jpg)

Quadrant D, selection 7: [https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/f15/2966,4078,881,1235/pct:70/0/native.jpg](https://gallica.bnf.fr/iiif/ark:/12148/btv1b105325870/f15/2966,4078,881,1235/pct:70/0/native.jpg)


