#!/bin/bash

if [ $# -ne 2 ];
then
	echo "Ivalid arguments"
	echo "Usage: ./simplify_7z.sh destination.7z source-folder-or-file"
	exit 1
fi

if [ -e $1 ];
then
	echo "Destination file $1 already exists"
	exit 1
fi

if [ ! -f $2 ] && [ ! -d $2 ];
then
	echo "Source file $2 does not exist"
	exit 1
fi

if [[ ! $1 =~ \.7z$ ]];
then
	echo "Destination file should have .7z extension (destFile.7z)"
	exit 1
fi

7z a -t7z -m0=lzma2 -mx=9 -mfb=64 -md=32m -ms=on -mhe=on -p $1 $2
