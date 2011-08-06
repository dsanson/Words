# William Whitaker's Words: a Latin-English Dictionary

This repository is a rehosting of the source files for version 1.97FC of Words. The original can be found [here][]. It is open source. Quoting from [wordsdoc.htm][]:

> This is a free program, which means it is proper to copy it and pass it on to your friends. Consider it a developmental item for which there is no charge. However, just for form, it is Copyrighted (c). Permission is hereby freely given for any and all use of program and data. You can sell it as your own, but at least tell me.

and later in the same document:

> Licence
>
> All parts of the WORDS system, source code and data files, are made freely available to anyone who wishes to use them, for whatever purpose.

William Whitaker passed away in late 2010. Here is his [obituary][]. I had no connection to him. I'm just a long time user of this great piece of software, who doesn't want to see it disappear now that he is no longer around to maintain it. So I am putting these source files up on Github in part to ensure that they will still be available if and when his website goes down. I suppose I also hope that someone might be interested in taking up the project and continuing to maintain it, and figure that putting the source on Github is one way to try to encourage that.

In addition to the source, I've included three [binary builds of words](https://github.com/dsanson/Words/tree/master/binaries): copies of the DOS and Windows binaries provided by Whitaker on his own site, and a universal binary for OS X that I built myself, that works with Lion.

Words is written in [Ada][]. I was able to compile a the source on a Mac by downloading and installing [GNAT GPL Edition 2011][]. Instructions for building words (and a lot of detailed information about what it does) can be found in [wordsdoc.htm]. That file is also include with the source posted here. First, you'll want to run:

	gnatmake -O3 words
	gnatmake makedict
	gnatmake makestem
	gnatmake ewdsefil
	gnatmake makeinfl

This produces four executables: `words`, `makedict`, `makestem`, `ewdsefil`, and `makeinfl`. You then need to run

	makedict DICTLINE.GEN
	makestem STEMLIST.GEN
	ewdsefil EWDSLIST.GEN
	makeinfl INFLECTS.LAT

This generates five new files,

	DICTFILE.GEN
	STEMFILE.GEN
	INDXFILE.GEN
	EWDSFILE.GEN
	INFLECTS.SEC

To run, words needs to be executed from a directory containing those five files along with

	ADDONS.LAT
	UNIQUES.LAT



  [here]: http://users.erols.com/whitaker/wordsdev.htm
  [wordsdoc.htm]: http://users.erols.com/whitaker/wordsdoc.htm
  [obituary]: http://www.legacy.com/obituaries/mywesttexas/obituary.aspx?n=william-whitaker&pid=147336402
  [Ada]: http://www.sigada.org/
  [universal binary for OS X]: http://files.davidsanson.com/words-os-x-universal.zip
  [GNAT GPL Edition 2011]: http://libre.adacore.com/libre/tools/gnat-gpl-edition/
