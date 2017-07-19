# XML Explorer
## Project Description
XML Explorer is an extremely fast, lightweight XML file viewer. It can handle extremely large XML files. It has been tested on files as big as 300MB. It allows fast viewing and exploration, copying of formatted XML data, evaluation of XPath expressions, and XSD schema validation.

It validates XML documents using XSD Schema (specified in the document), shows a list of validation errors, and double-clicking an error navigates and selects the node.

An expression library is included to store and manage commonly-used XPath expressions, much like Bookmarks in FireFox. It supports multiple document tabs, with support for middle-clicking to close tabs, and fully-featured, Visual Studio-style dockable panes.

![XML Explorer.png](https://raw.githubusercontent.com/Spetnik/XMLExplorer/master/XML%20Explorer.png)

XML Explorer does not currently have any edit capabilities. If you need to edit XML files, I highly recommend the excellent XML Notepad.

For more information and a walk-through of the code, see the Code Project article at http://www.codeproject.com/Articles/19555/XML-Explorer.

XML Explorer uses DockPanel Suite, a docking library for .NET Windows Forms development which mimics Visual Studio .NET. Many thanks to the contributors of the project!

## Performance

I've compared the times required to load XML files of varying size. XML Notepad was used for comparison, since it's nice enough to provide load times in the status bar. I realize the comparison isn't exactly fair, as XML Notepad is an XML editor. I trust you will find a place in your XML toolbox for both applications, as I have.

| File Size | XML Notepad | XML Explorer |
| --------- | ----------- | ------------ |
| 47.4 MB | 48.68 seconds | 4.94 seconds |
| 31.3 MB | 18.46 seconds | 3.63 seconds |
| 30.96 MB | 16.47 seconds | 2.89 seconds |
| 3.69 MB | 1.55 seconds | .32 seconds |
| 281 KB | .35 seconds | .04 seconds |

As you can see, the difference is greatest on extremely large files. On the more normal sized files, the difference is barely noticeable.

## Memory

XML Explorer also makes much more efficient use of RAM, by utilizing XPathDocument (instead of XmlDocument), and by loading the XML document into the display on-demand.

| File Size | XML Notepad | XML Explorer |
| --------- | ----------- | ------------ |
| 47.4 MB | 563.3 MB RAM | 126.1 MB RAM |
| 31.3 MB | 322.98 MB RAM | 73.92 MB RAM |
| 3.69 MB | 51.87 MB RAM | 14.04 MB RAM |
| 281 KB | 12.87 MB RAM | 6.85 MB RAM |

-Jason Coon
Last edited Jan 22, 2015 at 8:15 AM by jcoon, version 19
