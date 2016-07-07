# LabelImg

[![Build Status](https://travis-ci.org/tzutalin/labelImg.png)](https://travis-ci.org/tzutalin/labelImg)

LabelImg is a graphical image annotation tool.

It is written in Python and uses Qt for its graphical interface.

The annotation file will be saved as an XML file. The annotation format is PASCAL VOC format, and the format is the same as [ImageNet](http://www.image-net.org/)

![](icons/demo.png)

[![Demo video](https://j.gifs.com/4xy9z2.gif)](https://www.youtube.com/watch?v=p0nR2YsCY_U&feature=youtu.be)

## Dependencies
* Linux/Ubuntu/Mac

Requires at least [Python 2.6](http://www.python.org/getit/) and has been tested with [PyQt
4.8](http://www.riverbankcomputing.co.uk/software/pyqt/intro).

In order to build the resource and assets, you need to install pyqt4-dev-tools:

`$ sudo apt-get install pyqt4-dev-tools`

`$ make all`

`$ ./labelImg.py`

* Windows

Need to download Miniconda 2.7 64-bit Windows installer [from Miniconda website] (http://conda.pydata.org/miniconda.html).
Install for all users and add Python to PATH (through installer).

Run the following commands from elevated command prompt (cmd.exe):

```
conda install pyqt lxml numpy
(conda install -c anaconda pyqt=4.11.4)
conda install anacondaclient
conda install -c https://conda.anaconda.org/menpo opencv
```

because of a [bug] (https://groups.google.com/a/continuum.io/forum/#!topic/anaconda/qZBd_tYWY84) edit
in Minicona2/Scripts/pyrcc4.bat the line:

```
"%~dp0\..\Lib\site-packages\PyQt4\pyrcc4" %*
```
to
```
"%~dp0\..\Library\bin\pyrcc4" %*
```

(or alternate
download and setup [Python 2.6](https://www.python.org/downloads/windows/) or later and [PyQt4](https://www.riverbankcomputing.com/software/pyqt/download).)

Also, you need to install other python dependencies.
 
Open cmd and go to [labelImg]

`$ pyrcc4 -o resources.py resources.qrc`

`$ python labelImg.py`

## Usage
After cloning the code, you should run `$ make all` to generate the resource file.

You can then start annotating by running `$ ./labelImg.py`. For usage
instructions you can see [Here](https://youtu.be/p0nR2YsCY_U)

At the moment annotations are saved as an XML file. The format is PASCAL VOC format, and the format is the same as [ImageNet](http://www.image-net.org/)

You can also see [ImageNet Utils](https://github.com/tzutalin/ImageNet_Utils) to download image, create a label text for machine learning, etc


### General steps from scratch

* Build and launch: `$ make all; python labelImg.py`

* Click 'Change default saved annotation folder' in Menu/File

* Click 'Open Dir'

* Click 'Create RectBox'

The annotation will be saved to the folder you specify

### Create pre-defined classes

You can edit the [data/predefined_classes.txt](https://github.com/tzutalin/labelImg/blob/master/data/predefined_classes.txt) to load pre-defined classes

### Hotkeys

* Ctrl + r : Change the defult target dir which saving annotation files

* Ctrl + n : Create a bounding box

* Ctrl + s : Save

* n : Next image

* p : Previous image

### How to contribute
Send a pull request

### License
[License](LICENSE.md)

