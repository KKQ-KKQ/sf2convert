# sf2convert
### Convert SF2 SoundFonts to SF3 (Vorbis) or SF4 (FLAC) and back 

This utility converts SF2 files to SF3 format, using Ogg Vorbis for sample compression (SF3 is natively supported by MuseScore). Conversion of SF3 back to SF2 is also possible, however since Ogg Vorbis is lossy, the format is not useful for archiving purposes.

SF3 can contain lossless FLAC file. Actually MuseScore can open a SF3 which contains FLAC. sf2convert converts SF2 files to SF3 format using FLAC.

Based on the SoundFont reader/writer class by Davy Triponney (2015, [Polphone](https://github.com/davy7125/polyphone)), Werner Schweer and others (2010, [MuseScore](https://github.com/musescore/MuseScore)), which was ported from Qt to the [Juce framework](https://www.juce.com) and somewhat extended in order allow for easy integration with Juce-based projects. It makes use of the Vorbis and FLAC classes of Juce. In order to compile sf2convert, you'll' need Juce version 4. As a result, sf2convert compiles and runs on Mac, Windows, Linux and more.

## Bugs
The original sf2convert has a bug.
Invalid SF3 or SF4 is created by the original.
In this fork, the bug is fixed.
The file may be fixed if you extract SF3/SF4 by this utility, 


## Usage

Compression with Ogg Vorbis (o)

`sf2convert -zo <infile.sf2> <outfile.sf3>`

Compression with FLAC (l)

`sf2convert -zl <infile.sf2> <outfile.sf3>`
    
Extraction of any compressed format:

`sf2convert -x <infile.sf?> <outfile.sf2>`

For additional options, run the utility with an empty option.


## Notes

Try the following command if you cannot run the utility on MacOS.

`xattr -c sf2convert`


## How To Compile

The SoundFont class was ported to Juce and thus can be integrated with Juce projects rather easily. To compile, you need to get Juce 4 and use Projucer to create project exporters for your target platform.

## License

Released by Cognitone under GPLv2.
