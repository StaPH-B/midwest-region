---
layout: default
---

## Working with sequencing data

#### Sequencing file types
------------

##### BCL files
BCL or Binary Base Call format is the raw datafile for illumina sequencing that holds the basecalls and quality. These files are created and updated in realtime as the machine is sequencing and are used to generate the fastq files.

##### .fastq / .fastq.gz files

Fastq files are files that contain sequence data and quality information. The .gz extension just informs you the file is compressed, to be covered later. It is the format in which sequencing data is most often kept in. The file is structured with each read labeled with '@'. The following line has the sequence bases for that read. The 3rd line has a '+', and the 4th line has the sequence quality (Phred score) for each base encoded in a letter format.

example of two reads:
```
@M03478:141:000000000-C5B4D:1:1101:25956:10945 1:N:0:1
TTCCGTATTCATGCAACCTATGATGAAAGTATTAGTCGGTTACTCAATGTATTTGAGCGC
+
ABBBBCFFFFFFGGGGGGGGGG5GHHHHHGGHHHHHHGGGGFHHHHHHHHHHHHHFGHGG

@M03478:141:000000000-C5B4D:1:1101:26997:10945 1:N:0:1
ATTAAGCCAGTCTGGGCTTTGGGCAATTACAGTACCAAAGCAATATGGTGGTGCCGAAGT
+
CCCCCFFFFFFFGGGGGGGGGGGHHGHHHHHHHHHHHHHHHHHHHHHHGHGEFHHEFGGF
```

The label has the following information:
**Sequence Identifier**
M03478:141:000000000-C5B4D:1:1101:25956:10945
* **M03478** - the unique instrument name
* **141** - the run id
* **000000000-C5B4D** - flowcell id
* **1** - flowcell lane
* **1101** - tile number on the flowcell
* **25956** - x-coordinate of the cluster within the tile
* **10945** - y-coordinate of the cluster within the tile

**Sequence Description**
1:N:0:1
* **1** - the member of a read pair '1' is forward '2' is reverse
* **N** - the read is filtered 'Y' or "N"
* **0** - If the read is not identified as a control, then the value is zero. If the read is identified as a control, the number is greater than zero, and the value specifies what type of control it is.
* **1** - sample number from the sample sheet

From this information we can determine that both of reads shown above are fwd reads from the same flowcell tile in the same y position but different x positions.

###### phred score
Here is a break down of how the quality score is encoded on the read:
A phred score of 10 translates to a 1 in 10 chance of an incorrect basecall or 90% accuracy:
* 10 	1 in 10 	90%
* 20 	1 in 100 	99%
* 30 	1 in 1000 	99.9%
* 40 	1 in 10,000 	99.99%
* 50 	1 in 100,000 	99.999%
* 60 	1 in 1,000,000 	99.9999%

These are encoded on in the fastq as shown below
```
SSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSS.....................................................
 ..........................XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX......................
 ...............................IIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIII......................
 .................................JJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJ.....................
 LLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLL....................................................
 !"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ[\]^_`abcdefghijklmnopqrstuvwxyz{|}~
 |                         |    |        |                              |                     |
33                        59   64       73                            104                   126
 0........................26...31.......40                                
                          -5....0........9.............................40
                                0........9.............................40
                                   3.....9..............................41
 0.2......................26...31........41                              

S - Sanger        Phred+33,  raw reads typically (0, 40)
X - Solexa        Solexa+64, raw reads typically (-5, 40)
I - Illumina 1.3+ Phred+64,  raw reads typically (0, 40)
J - Illumina 1.5+ Phred+64,  raw reads typically (3, 41)
    with 0=unused, 1=unused, 2=Read Segment Quality Control Indicator (bold)
    (Note: See discussion above).
L - Illumina 1.8+ Phred+33,  raw reads typically (0, 41)
```
Using the Illumina 1.8+ encoding a seeing an H in the fastq corresponds to a Phred score of 40. While a 0 corresponds to a Phred score of 15.

##### .fasta files

The fasta file format is a method of storing sequence data that has been assembled. The format includes a '>' that contains the sequence label followed by the sequence on the next line(s). The file can contain multiple sequences "multi-fasta" with each sequence starting with a '>'.

example of a couple of lines from the NP and NS segments of an influenza virus:
```
>A/Hong_Kong/4801/2014_834574_NP
gttaataatcactcactgagtgacatcaaagtcatggcgtcccaaggcaccaaacggtcttatgaacagatggaaactga
tggagatcgccagaatgcaactgagattagggcatccgtcgggaagatgattgatggaattgggagattctacatccaaa
>A/Hong_Kong/4801/2014_834575_NS
gtgacaaagacataatggattccaacactgtgtcaagtttccaggtagattgctttctttggcatatccggaaacaagtt
gtagaccaaaaactgagtgatgccccattccttgatcggcttcgccgagatcagaggtccctaaggggaagaggcaatac
```

##### .sam / .bam files

The sam (Sequence Alignment Map) and bam (Binary Alignment Map) file format is a format that allows you to store the reads from a fastq mapped to a reference sequence. The sam and bam files are the same except the bam file is a binary format so it cannot be read by a human. The binary format is useful because it can be compressed to take up less disk space and can be read by programs more easily.

If you are interested in learning more about what is in this file format please visit this [wiki article](https://en.wikipedia.org/wiki/SAM_\(file_format%29) on the topic.

##### other file formats

There are many other files like .vcf (variant call format) or the .gff (GenBank Flat File Format). These other types can have many uses, but the fastq/fasta/bam files are the ones most often encountered.

#### Sequencing file compression
------------

File compression is simple a method of storing a file that has been reduced in size. This can apply to any file type including sequence data, music, videos, or whatever you keep on your computer. There are many types of file compression each with it's own set of pro's and con's. When working with sequencing data here a couple that are commonly used:

* zip (.zip) - a very common universal method of compressing things in the Windows environment not used very often for sequence data. Can compress multiple files or folders.
* tar (.tar) - a method of wrapping multiple files and folders together in linux. Doesn't apply any compression.
* gzip (.gz) - a very common universal method of compressing things in the linux environment, used a lot for compressing fastq files. Can only compress a single file so it is often used in combination with tar (.tar.gz).
* bgzip (.gz) - very similar to gzip but has added features that are used specifically for sam file formats. Often adds a bit of confusion since gzip cannot interact with these files.

File compression is an important part of bioinformatics since the files are often very large. Here is some examples of the data sizes involved and how much of a difference compression can help.

**Compressed:**
* *E coli* both set of reads ~200MB
* *E coli* sequencing run (16 isolates) ~4GB

**Uncompressed:**
* *E coli* both set of reads ~900MB
* *E coli* sequencing run (16 isolates) ~20GB

#### How data is transferred
------------

Sequencing data can be moved a number of ways. The most common approach to transferring data is **SFTP**. Interacting with databases and cloud utilities often have their own methods for transferring files securely and without loss but these methods often use a version of FTP, FTPS, HTTP, HTTPS, SCP, or SFTP.

* **FTP** or File Transfer Protocol is pretty universal but is not secure and does not comply with HIPAA regulations.
* **HTTP** or HyperText Transfer Protocol often used for accessing websites, is widely used but is insecure.
* **FTPS** or File Transfer Protocol over Secure Sockets Layer, the same as FTP but adds a layer of security
* **HTTPS** or HyperText Transfer Protocol over Secure Sockets Layer, the same as HTTP but with a layer of security. Side note: always look for the HTTPS:// when using websites that ask for either a login or personal information.
* **SFTP** or Secure File Transfer Protocol is a method of transferring files through an SSH or Secure Shell connection. SSH creates a secure connection through an unsecure network (most often the internet). This connection allows two computers to communicate across a network with confidentiality and integrity of data.
* **SCP** or Secure Copy is very similar to SFTP but more primitive. It can only transfer files it cannot do other things like delete files which SFTP can do.

Of all these methods **SFTP** is the most commonly used in Bioinformatics as it provides the most secure environment that allows the safe transfer of data.
