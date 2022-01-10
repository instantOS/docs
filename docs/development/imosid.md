# imosid

imosid stands for "instant manager of sections in dotfiles". 

It aims to be an unobtrusive dotfile manager used by linux distributions or
automated config systems that does not interfere with user customisation. It
allows applying updates to dotfiles while detecting parts modified by users in
order to not overwrite them. 



## General information

Imosid works by dividing dotfiles into sections marked by special comments. These
sections can be updated, deleted or modified independently of one another. A section
can have two states, unmodified and modified. Modified sections are ignored by
imosid but do not interrupt or otherwise impact the processing of other
unmodified sections. 

For a section to be considered unmodified it needs intact beginning and ending
markers and a comment that contains the hash of the section content.  If any of
the marker comments have incorrect syntax, are missing or the hash of the
section content does not match the hash in the comment then the section is
considered modified. 

Again, breaking the syntax of a section or modifying any part of it still leaves
other sections fully functional and processable by imosid. 

## Terminology

### Updating a section

Replace the section content with something different and update the hash
comment. The new content is often from a newer (completely unmodified) version
of the same file

### Compiling a section

Insert/modify a hash comment to match the section content and create an
unmodified section. Used to create files that are used as update sources. 

## Section syntax

Imosid supports a wide range of different file formats and automatically
detects the comment syntax. This means that all imosid comments start with //
if the file being processed is c source code and \# if the file is a shell
script. For the purposes of all examples, // will be used as the placeholder
for any kind of language/format specific commenting syntax.

All imosid comments begin with the comment syntax followed by "..."  and the
name of the section they are a part of.

Example
```txt
//...helloworld begin
```
This marks the beginning of the section hello world

## Metafiles

Some file formats do not allow for comments either because they have no defined
comment syntax or because the application using the the file removes comments
(please stop that flameshot!). In order to not force the use of other dotfile
managers for files without comments metadata imosid records information about
them in a separate filename.imosid.toml file. This approach provides some basic
imosid functionality without comments but does not allow for multiple sections
in one file.

## Commands

### update

```sh
imosid update targetfile
```

- updates target file from sources
- requires upstream source comments

Example

hello.txt
```txt
#...sectionname2 begin
#...sectionname2 hash asduvhnw42377
#...sectionname2 source https://example.com/myfile.txt
Content
#...sectionname2 end
```

``` sh
imosid update hello.txt 
```

This command will fetch  https://example.com/myfile.txt  and if that file
contains a section called sectionname2  it will update the section in hello.txt
to match sectionname2 in https://example.com/myfile.txt. 

### Apply

```sh
imosid apply sourcefile
```

- requires target comment
- applies all sections present in all files

### Compile

```sh
imosid compile
```

- regenerates section hashes
- creates main section if not present already
  - respect special 1st line like hashbangs

### check

```sh
imosid check /path/to/dotfiles_directory
```

## Problems

- section updates can clash with existing configs
  - duplicate key detection?
  - keep sections to a single function?


## Syntax

```txt
#... all target /path/to/targetfile
#...sectionname begin
#...sectionname hash 123aojd981uenc821y3
#...sectionname source /usr/share/instantdotfiles/stuff
Content
#...sectionname end

#...sectionname2 begin
#...sectionname2 hash asduvhnw42377
#...sectionname2 source https://raw.github.stuff
Content
#...sectionname2 end

```

## Installation from source

```sh
git clone https://github.com/instantOS/imosid
cd imosid
cargo build --release
```

## Disclaimer

**imosid is my first time using rust, the program is in an extremely basic state.
Syntax and options are still subject to change**

