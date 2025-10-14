# Challenge Description
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?

Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/99/flag2of2-final.pdf).
# Thought Process & Solution
My first step was to just open the file and see if there are any useful hints and we see somthing:
```bash
1n_pn9_&_pdf_2a6a1ea8}
```
Looks like we have a part of the flag.

```bash
chaos@Chaos:/mnt/c/Users/asus/Desktop/stp/forensics/polyglot$ strings flag2of2-final.pdf
IHDR
iCCPICC profile
byY%>'
\W<~
C`$G
        pHYs
tIME
tEXtComment
Created with GIMPW
{IDATh
Z@DL
<E3
RJ)ya
% ;@
TvI~
,Ugi
-oF 8
)ZFd{B
::nM/
3"RJE
IEND
%PDF-1.4
%%Invocation: path/gs -P- -dSAFER -dCompatibilityLevel=1.4 -q -P- -dNOPAUSE -dBATCH -sDEVICE=pdfwrite -sstdout=? -sOutputFile=? -P- -dSAFER -dCompatibilityLevel=1.4 ?
5 0 obj
<</Length 6 0 R/Filter /FlateDecode>>
stream
^endstream
endobj
6 0 obj
endobj
4 0 obj
<</Type/Page/MediaBox [0 0 595 842]
/Rotate 0/Parent 3 0 R
/Resources<</ProcSet[/PDF /Text]
/Font 8 0 R
/Contents 5 0 R
endobj
3 0 obj
<< /Type /Pages /Kids [
4 0 R
] /Count 1
endobj
1 0 obj
<</Type /Catalog /Pages 3 0 R
/Metadata 9 0 R
endobj
8 0 obj
<</R7
7 0 R>>
endobj
7 0 obj
<</BaseFont/Helvetica/Type/Font
/Subtype/Type1>>
endobj
9 0 obj
<</Type/Metadata
/Subtype/XML/Length 1173>>stream
<?xpacket begin='
' id='W5M0MpCehiHzreSzNTczkc9d'?>
<?adobe-xap-filters esc="CRLF"?>
<x:xmpmeta xmlns:x='adobe:ns:meta/' x:xmptk='XMP toolkit 2.9.1-13, framework 1.6'>
<rdf:RDF xmlns:rdf='http://www.w3.org/1999/02/22-rdf-syntax-ns#' xmlns:iX='http://ns.adobe.com/iX/1.0/'>
<rdf:Description rdf:about="" xmlns:pdf='http://ns.adobe.com/pdf/1.3/' pdf:Producer='GPL Ghostscript 10.01.2'/>
<rdf:Description rdf:about="" xmlns:xmp='http://ns.adobe.com/xap/1.0/'><xmp:ModifyDate>2024-03-12T00:04:34Z</xmp:ModifyDate>
<xmp:CreateDate>2024-03-12T00:04:34Z</xmp:CreateDate>
<xmp:CreatorTool>UnknownApplication</xmp:CreatorTool></rdf:Description>
<rdf:Description rdf:about="" xmlns:xapMM='http://ns.adobe.com/xap/1.0/mm/' xapMM:DocumentID='uuid:a84b09c2-1820-11fa-0000-a10f4530f20a'/>
<rdf:Description rdf:about="" xmlns:dc='http://purl.org/dc/elements/1.1/' dc:format='application/pdf'><dc:title><rdf:Alt><rdf:li xml:lang='x-default'>Untitled</rdf:li></rdf:Alt></dc:title></rdf:Description>
</rdf:RDF>
</x:xmpmeta>


<?xpacket end='w'?>
endstream
endobj
2 0 obj
<</Producer(GPL Ghostscript 10.01.2)
/CreationDate(D:20240312000434Z00'00')
/ModDate(D:20240312000434Z00'00')>>endobj
xref
0 10
0000000000 65535 f
0000000563 00000 n
0000001969 00000 n
0000000504 00000 n
0000000363 00000 n
0000000182 00000 n
0000000345 00000 n
0000000656 00000 n
0000000627 00000 n
0000000720 00000 n
trailer
<< /Size 10 /Root 1 0 R /Info 2 0 R
/ID [<790F02A2E161719EEFC663CD15373CB0><790F02A2E161719EEFC663CD15373CB0>]
startxref
2095
%%EOF
```
Nothing from strings so its likely that something is appended/hidden inside the file. A quick binwalk scan should reveal something.

> For some reason i cant use my VM for now so i will switch to wsl or online tools.

<img width="1263" height="464" alt="image" src="https://github.com/user-attachments/assets/8071c156-71ea-40a6-9603-68e4c0decde7" />

So from the analysis we do see two files embedded inside our pdf.
Upon saving the PNG file and opening it we see first half of the flag - 

<img width="538" height="478" alt="image" src="https://github.com/user-attachments/assets/ec9223eb-3d34-4b1b-841c-031402a3e7c7" />

**Flag:** `picoCTF{f1u3n7_1n_pn9_&_pdf_2a6a1ea8}`
## New Learning
Binwalk - its a tool for reverse engineering binary files to identify and extract embedded files, executable code, and compressed data. It functions something similar to the file command - by reading the HEX code of the file cross checking with known file signatures.
## Reference
