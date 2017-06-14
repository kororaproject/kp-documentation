# Working with Archives

At some point, you will probably have to deal with a compressed archive file. Archives allow you to lump multiple files or directories together into a single file, making it easier for transportation.

## Archive Types and Extensions

Because there are multiple types of archives (they often vary by the kind of compression algorithm used), the easiest way to distinguish one over the other is via its file extension. Below are some of the most common archive formats used and their extensions:

Archive Format | Extension
--- | ---
compress | .Z
zip | .zip
lzip | .lz
xz | .xz
lzma | .lzma
bzip | .bz2
tar | .tar
tar ( gzip compression) | .gz, .tgz
tar (bzip2 compression) | .bz2

### Tar

The most common type of archive in the UNIX/Linux world is the tape archive or **tar** file, sometimes called a **tarball**. tar is heavily used due to its history and flexibility. While the packaging format will remain the same, the type of compression used on compressed tar archives can be changed at runtime in order to accommodate better compression or better performance.

### Zip

The zip archive format was originally designed for DOS and Windows systems, and is still used heavily within those operating systems. However, zip archives are readable on Linux as well, and can be easily extracted using the `unzip` command.

## Within the File Manager

Most File Managers allow direct creation or extraction of recognized archives without needing to enter the Terminal. 

### Creating an Archive
To create an archive, highlight a file, a series of files, or a directory, and right click on the selection. Then select the **Compress...** option. You may be prompted for what kind of archive to create, and what kind of compression, if any, to use.

### Extracting an Archive

To extract an existing archive that you have already created or downloaded, right-click on the archive file inside your File Manager. Select the option **Extract**. If the File Manager recognizes the extension, it will attempt to extract the contents of the archive automatically. If the archive has been protected or encrypted with a password, you may be prompted to enter the password before the archive's contents can be completely extracted.

Alternatively, your desktop environment likely has an Archive Manager application pre-installed. In which case, simply double-clicking the archive should launch the Archive Manager and allow you to extract its contents.

## Within the Terminal

Should you ever need to manipulate archives (for instance, if you want to run a program whose installation instructions reads "Untar this package and run the installer script"), it couldn't hurt to be able to do it in a terminal.

### Creating an Archive

As mentioned previously, the most common archive format is the tarball with some kind of compression. To create a basic tarball, enter the following command:

    tar [options] destination_file inputfile1 inputfile2....

For example, to create a tarball called "archive.tar" containing files file1, file2, and file3, issue the following command:

    tar cfv archive.tar file1 file2 file3
	
If you want the contents of the archive to be compressed so that they take up less space, you can pass one of the compression flags to the tar command. For instance, to use gzip compression within the tarball, you would type the following:

    tar cfvz archive.tgz file1 file2 file3
	
In the above command, we passed a `-z` flag to the tar command so that the program would use `gzip` compression on the archive. We also changed the output file's extension to **.tgz** instead of **.tar** so that it is obvious to anyone looking at the file what kind of compression it uses.

We could similarly use another algorithm like bzip2 instead of gzip if we want a slightly higher rate of compression:

    tar cfvj archive.bz2 file1 file2 file3
	
In this case, we used `-j` instead of `-z` to trigger bzip2 compression, and also changed the extension of the archive to **.bz2**.

**NOTE**: 
Take careful note of the order in which the arguments are passed to the tar command. The destination archive name comes **before** the files that will go into the archive. This may seem to go against many other commands that generally go in the format `command source destination`, but it makes sense when you consider that the tarball is expected to contain multiple files. As such, variable arguments may be thrown at the program without fundamentally changing the syntax. For example:

    tar cfvz archive.tgz file1 file2 file3
    tar cfvz archive.tgz file1 file2 directory1 directory2
    tar cfvz archive.tgz file1 file2 file3 file4 file5
    tar cfvz archive.tgz file* dir*
	tar cfvz archive.tgz ./*
	
All of the above are valid and maintain consistent syntax, even though the number of files being archived changes.


### Extracting an Archive

To extract the contents of a tarball, use the `-x` flag (Short for "e**X**tract"), along with any additional flags necessary to specify the type of compression used. For example, to extract a basic, non-compressed tarball, you would type the following:

    tar xfv archive.tar

The `-v` flag is not necessary, it simply echoes back the contents of the tarball as it extracts them. If the tarball is compressed, you may need to add an additional flag to the command. For instance, to extract a gzip-compressed .tar.gz/.tgz file, you would add a `-z` flag and use the following command:

    tar xfvz archive.tgz
	
To extract a bzip2 tarball, you would add a `-j` and use the following:

    tar xfvj archive.bz2
	
**Pro-Tip**: The tar program is usually intelligent enough to figure out what kind of archive it's processing if the archive is in a supported format. And so if you are not concerned about creating tarballs but only need to extract them, you can drop the compression flag and let the tar command figure out which one to use. `tar xfv` will work on a .tar, .tgz, .bz2, and others without explicitly specifying a `-z` or `-j`. So the next time you need to extract a tarball, try just entering the following:

    tar xvf archive.XXX

where `.XXX` is the extension of the archive.