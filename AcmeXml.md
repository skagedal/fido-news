Current plan is to write a wrapper for libxml2's Reader in C, using a ECMA-like API, and to write a new Writer, possibly inspired by Mono code.  The Mono test code, very useful.  Convert to [GLib](https://developer.gnome.org/glib/2.36/glib-Testing.html). Will want to have some assert macros of our own, see [gtestutils.h](https://git.gnome.org/browse/glib/tree/glib/gtestutils.h?h=glib-2-36).

## Mono code ##
  * [System.Xml](https://github.com/mono/mono/tree/master/mcs/class/System.XML/System.Xml)
  * **Reader:**
    * [XmlReader](https://github.com/mono/mono/blob/master/mcs/class/System.XML/System.Xml/XmlReader.cs) ([docs](http://docs.go-mono.com/?link=T%3aSystem.Xml.XmlReader)) is the base class
    * [XmlTextReader](https://github.com/mono/mono/blob/master/mcs/class/System.XML/System.Xml/XmlTextReader.cs) ([tests](https://github.com/mono/mono/blob/master/mcs/class/System.XML/Test/System.Xml/XmlTextReaderTests.cs)) is the core implementation ([XmlTextReader2](https://github.com/mono/mono/blob/master/mcs/class/System.XML/System.Xml/XmlTextReader2.cs) is a .NET 2.0 wrapper)
    * [XmlReaderSettings](https://github.com/mono/mono/blob/master/mcs/class/System.XML/System.Xml/XmlReaderSettings.cs) ([docs](http://docs.go-mono.com/?link=T%3aSystem.Xml.XmlReaderSettings))
  * **Writer:**
    * [XmlWriter](https://github.com/mono/mono/blob/master/mcs/class/System.XML/System.Xml/XmlWriter.cs) ([docs](http://docs.go-mono.com/?link=T%3aSystem.Xml.XmlWriter)) - base class
    * [XmlTextWriter](https://github.com/mono/mono/blob/master/mcs/class/System.XML/System.Xml/XmlTextWriter2.cs) ([docs](http://docs.go-mono.com/?link=T%3aSystem.Xml.XmlTextWriter)) ([tests](https://github.com/mono/mono/blob/master/mcs/class/System.XML/Test/System.Xml/XmlTextWriterTests.cs)) - implementation
    * [XmlWriterSettings](https://github.com/mono/mono/blob/master/mcs/class/System.XML/System.Xml/XmlWriterSettings.cs) ([docs](http://docs.go-mono.com/?link=T%3aSystem.Xml.XmlWriterSettings))

## Mono issues ##
  * Docs for [WriteEntityRef](http://docs.go-mono.com/?link=M%3aSystem.Xml.XmlWriter.WriteEntityRef) says it writes ` %name; `, [code](https://github.com/mono/mono/blob/master/mcs/class/System.XML/System.Xml/XmlTextWriter2.cs) writes ` &name; ` and that's what [.NET](http://msdn.microsoft.com/en-us/library/system.xml.xmltextwriter.aspx) does.

## libxml2 ##
  * Reported bugs:
    * [xmlSetStructuredErrorHandler vs. xmlSetErrorHandler](https://bugzilla.gnome.org/show_bug.cgi?id=708122) - doc problem
    * [xmlTextReaderReadState returns EOF when there are still nodes to be read](https://bugzilla.gnome.org/show_bug.cgi?id=708125)
    * [No way to move cursor back to attribute from xmlTextReaderReadAttributeValue](https://bugzilla.gnome.org/show_bug.cgi?id=708488)
## Useful things ##
  * [XMLStarlet](http://xmlstar.sourceforge.net/)

## XML readers ##
  * [from LibreOffice](http://cgit.freedesktop.org/libreoffice/core/tree/xmlreader)