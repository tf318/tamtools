
# TAMtools Installation

TAMtools is a Python program that depends on:

* some third-party Python modules 
* [MUMmer 3](http://mummer.sourceforge.net/)
* [BWA Aligner](http://bio-bwa.sourceforge.net/)

## Python Dependencies

TAMtools is a standalone Python program. It depends on various system modules 
that are available in a default Python 2.x distribution, as well as on a few
third party modules. Run the following commands to install these latter
dependencies:

    pip install pysam
    pip install bx-python
    pip install tabulate

## MUMmer 3.0

The `tamtools makemap` command makes use of 
[MUMmer 3](http://mummer.sourceforge.net/). 
You must compile MUMmer as a 64-bit executable, not 32-bit. 
To do this, after downloading the source from the MUMmer web site,
 edit `MUMmer3.23/src/kurtz/libbasedir/types.h` and add the line:

    #define SIXTYFOURBITS

before the line 

    #ifdef SIXTYFOURBITS

Then `make install` as normal. Once you have compiled 64-bit MUMmer, 
add the location of the `mummer` binary to your `PATH` environment variable.


## BWA Aligner

The `tamtools hybridize` command makes use of 
[BWA Aligner](http://bio-bwa.sourceforge.net/). 
Once you have installed BWA, add the location of the `bwa` binary to 
your `PATH` environment variable.

Note: if you want to use a different aligner, you can either edit the 
`tamtools` source code as appropriate, or use the `tamtools partial` 
command and implement your own workflow as described in [README.md](README.md).
