Revcontrol
==========

Automatic version control.

### Examples
```
touch test.txt
nohup revcontrol test.txt &
```
An empty file named test.0001.txt is now created.

`echo "some text" >> test.txt`

Revcontrol now creates a new file named test.0002.txt with content "some text".

`echo " in a file" >> test.txt`

Yet another file named test.0003.txt wit content "some text in a file" is created. Etc. This lets you keep a complete revision history for your documents, without requiring manual 'pushes'.

### Dependencies
- inotifywait from the inotify-tools metapackage;
- OS X user should use [kqwait](https://github.com/sschober/kqwait) instead.

### Installation
- Resolve the dependencies. On Debian, this means:

`sudo apt-get install inotify-tools`

- place revcontrol in your PATH and make sure it's exectuable:

```
sudo cp revcontrol /usr/bin/
sudo chmod +x /usr/bin/revcontrol
```

### Usage
- To start watching:

`nohup revcontrol <filename> &`

- To stop watching, take note of the pid and kill it.

To avoid clutter, you'll probably want to give each document its own directory. [scribe](https://github.com/Antithesisx/scribe) automates this process for you.
