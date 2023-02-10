# autosrt <a href="https://pypi.python.org/pypi/autosrt"><img src="https://img.shields.io/pypi/v/autosrt.svg"></img></a>
  
### Auto-generated subtitles for any video
autosrt is a simple command line tool made with python to auto generate subtitle / closed caption for any video / movie or audio file and translate it automaticly for free using pygoogletranslation https://github.com/Saravananslb/py-googletranslation

this script is a modified version of original autosub made by Anastasis Germanidis at https://github.com/agermanidis/autosub


### Installation
if you don't have python on your Windows system you can get compiled version from https://github.com/botbahlul/autosrt/releases/download/autosrt-0.0.3/autosrt-0.0.3.zip

just extract those ffmpeg.exe and autosrt.exe into a folder that has been added to PATH ENVIRONTMET for example in C:\Windows\system32

you can get latest version of ffmpeg from https://www.ffmpeg.org/

in Linux you have to install this script with python (version minimal 3.8 ) and install ffmpeg with your linux package manager for example in debian based linux distribution you can type :

```
apt update
apt install -y ffmpeg
```

to install this autosrt, just type :
```
pip install autosrt
```

you can compile this script into a single executable file with pyinstaller by downloading __init__.py file, rename it to autosrt.py and type :
```
pip install pyinstaller
pyinstaller --onefile autosrt.py
```

the executable compiled file will be placed by pyinstaller into dist subfolder of your current working folder, so you can just rename and put that compiled file into a folder that has been added to your PATH ENVIRONTMENT so you can execute it from anywhere

I was succesfuly compiled it in Windows 10 with pyinstaller-5.1 and Pyhton-3.10.4, and python-3.8.12 in Debian 9

another alternative way to install this script with python is by cloning this git (or downloading this git as zip then extract it into a folder), and then just type :

```
python setup.py build
python setup.py install
```

you can also install this script (or any pip package) in ANDROID DEVICES via PYTHON package in TERMUX APP

https://github.com/termux/termux-app/releases/tag/v0.118.0

choose the right apk for your device, install it, then open it

type these commands to get python, pip, this autosrt, (and any other pip packages) :

```
termux-setup-storage
pkg update -y
pkg install -y python
pkg install -y ffmpeg
pip install autosrt
```

### Simple usage example 

```
autosrt --list-languages
autosrt -S zh-CN -D en "Episode 1.mp4"
```

### Usage

```
autosrt [-h] [-C CONCURRENCY] [-o OUTPUT] [-F FORMAT]
             [-S SRC_LANGUAGE] [-D DST_LANGUAGE]
             [-n RENAME] [-p PATIENCE] [-v]
             [--list-formats] [--list-languages]
             [source_path]

positional arguments:
  source_path           Path to the video or audio file

options:
  -h, --help            show this help message and exit
  -C CONCURRENCY, --concurrency CONCURRENCY
                        Number of concurrent API requests to make
  -o OUTPUT, --output OUTPUT
                        Output path for subtitles (by default, subtitles are saved in the same directory and name as the source path)
  -F FORMAT, --format FORMAT
                        Destination subtitle format
  -S SRC_LANGUAGE, --src-language SRC_LANGUAGE
                        Language spoken in source file
  -D DST_LANGUAGE, --dst-language DST_LANGUAGE
                        Desired language for the subtitles
  -n RENAME, --rename RENAME
                        rename the output file.
  -p PATIENCE, --patience PATIENCE
                        the patience of retrying to translate. Expect a positive number. If -1 is assigned, the program will try for
                        infinite times until there is no failures happened in the output.
  -V, --verbose         logs the translation process to console.
  -v, --version         show program's version number and exit
  -lf, --list-formats   List all available subtitle formats
  -ll, --list-languages
                        List all available source/destination languages
```

### License

MIT

Check my other SPEECH RECOGNITIION + TRANSLATE PROJECTS in https://botbahlul.github.io
