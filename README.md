## GoNote - terminal client for SimpleNote

GoNote is a simple utility for managing notes in your SimpleNote account. It allows basic operations like creating new notes - either by using external editor, piping file contents or just passing text in command line, aswell as listing, editing and deleting them. I'm probably one of many developers who use terminal on a daily basis and, in time, leaving it just to save some text for later became a nuisance. At the same time I like having all my notes available on my phone or in the browser, just in case I don't have my computer with me. SimpleNote is a very simple (doh) service which focuses on having very straightforward and transparent way of managing your notes, at the same allowing access from mobile devices and web - thus the reason for choosing it as a storage backend for this app.

### Installation
#### OSX
`brew tap exaroth/gonote`

`brew install gonote`

#### Linux

**AMD64**
`wget -O gonote https://github.com/exaroth/gonote/releases/download/0.1.0/gonote.amd64 && chmod +x gonote_test && sudo mv gonote /usr/local/bin/`

**i386**
`wget -O gonote https://github.com/exaroth/gonote/releases/download/0.1.0/gonote.i386 && chmod +x gonote_test && sudo mv gonote /usr/local/bin/`

#### Ubuntu

### Example Usage

- **Creating notes**

`gonote` - Will open external editor (by default vim) allowing you to create new note.

`gonote @sometag @anothertag` - Same as above but will also attach @sometag and @anothertag to the note

`gonote Something something dark side...` - Will create note with "Something something dark side..." content

`cat somefile.txt | gonote @sometag` - Saves contents of a note appending @sometag tag to it

- **Listing notes**

`gonote list` - Will list all notes in your SimpleNote account

`gonote list -n 5` - Lists last 5 notes

`gonote list --deleted` - List all notes including those that are in trash

- **Editing existing note**

`gonote edit <note_id>` - Edit not with given note id

- **Fetching note**

`gonote get <note_id>` - Will fetch a note with given id, retrieved with `list` command

- **Deleting note**

`gonote delete <note_id>` - Deletes a note, moving it to trash

`gonote delete <note_id> --permanently` - Will permanently delete a note.

### Configuration file
You can find configuration file in ~/.gonote.json.
Available options are:
- `email` - SimpleNote email
- `password` - SimpleNote password
- `editor` - editor to use (vim by default)
- `markdown` - whether to set markdown flag when uploading notes

