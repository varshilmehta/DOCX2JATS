# DOCX2JATS
Java project, aimed to facilitate DOCX to JATS XML transformation for scientific articles.

For now it uses [TEIC Stylesheets](https://github.com/TEIC/Stylesheets) for the hard work and Java standard library for the more subtle parsing of references, tables and figure captions etc. It is distributed under Creative Commons Attribution-ShareAlike 3.0
Unported License.

Also projects uses [saxon9he](http://saxon.sourceforge.net/) for OOXML to JATS XML transformation. It is distributed under Mozilla Public License version 1.0.

In the future releases it is planned to refuse from the third party software.

## How to use it?

1. Headings and Sub-headings etc  
Make sure that the headings and sub heading are proper.
Headings
For example: the docx of an original article file may have the following headings
a) Abstract
b) Introduction
c) Methods and Materials
d) Results
e) Discussion
f) Conslusion
g) References
Make sure you put each of these as heading 1 in the word file (just select the word and click on the Heading 1 on the top row which is displayed in the word file).

Subheadings
Each of these can have sub headings (Heading 2).
Instead of Heading 1, just select Heading 2.

If you want to add one more sub heading to the sub heading, make it Heading 3.


2. Bibliography as separete list at the end of the document. Title for bibliography should be written as "References" 
Refernces should be like this:

-Articles in Journals
    Mehta V, Agarwal S. Does Vitamin D Deficiency Lead to Hypertension?. Cureus. 2017;9(2):e1038. PMID: https://www.ncbi.nlm.nih.gov/pubmed/28357170. DOI: https://doi.org/10.7759/cureus.1038.
    or
    Mehta V, Pusukuru R, Ghodke B. Association of Thyroid Stimulating Hormone and Lipid Profile in Pregnancy. Journal Of Medical Research And Innovation. 2017;1(2):AU1-AU6. URI: http://jmri.org.in/index.php/jmri/article/view/50.

Books and Other Monographs

    Personal author(s): Ringsven MK, Bond D. Gerontology and leadership skills for nurses. 2nd ed. Albany (NY): Delmar Publishers;1996.
    or
    Editor(s), compiler(s) as author: Norman IJ, Redfern SJ, editors. Mental health care for elderly people. New York: Churchill Livingstone;1996.
    or
    Chapter in a book: Phillips SJ, Whisnant JP. Hypertension and stroke. In: Laragh JH, Brenner BM, editors. Hypertension: pathophysiology, diagnosis, and management. 2nd ed. New York: Raven Press; 1995. p. 465-78. 


Alternatively, you can download the JMRI customised endnote version from here: http://jmri.org.in/files/J%20Med%20Res%20Innov.ens


3. In-text citations should be pointed as [1], [2] or [3,4,5]. For now are supported only citations in square brackets.

4. In-text references for tables and figures are parsed if they mark as "tabl 1.", "table 1", "fig. 1", "figure" or cyrillic analogs.

5. Table and Figure titles for parsing are needed to be situated right above the table or figure. Example: "Table 1. Example table title". For captions there is a need to place them after table and figure and start caption with `*`. Example: `* This table caption will be parsed`

6. For best result bibliography list should be written in AMA or Vancouver citation style. Supports journal articles, books, chapters and conferences. Alternatively use JMRI customised endnote style.

7. Examples of well-formed docx files for parsing are presened in the root directory of the project: https://drive.google.com/open?id=1FhDoh7fnXK0P3d8TN7RNR2f9YybGIShB

## How to use?
Download and unpack the latest release: https://github.com/Vitaliy-1/DOCX2JATS/releases and
run as executable jar file. Please note that jar file and article docx file must be in one parent directory with stylesheets folder.
Archive contains 1.jar file and stylesheets folder, which need to be unziped into one directory. Because I am not good programmer, there is a need to place article in docx format in this folder before making transformation. Suppose archive is unzipped on the drive C in the jats folder. Input article article1.docx is also situated there. From windows cmd user need to go to this folder and enter:
`java -jar 1.jar article1.docx article1.xml`

From version 1.0.3 there is no need to copy input article to the folder, where is executable jar file situated. But if one points the full path to the jar file, path to the input article must also be absolute. Otherwise the programm would not find stylesheets folder, e.g.:
`java -jar 1.jar D:\article\article1.docx article1.xml` or `jar -jar C:\DOCX2JATS\1.jar D:\article\article1.docx article1.xml` 

Please not, that the user must have permissions to write to the specified output folder. 
