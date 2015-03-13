# Useful software #

See also [[OtherNewsReaders](OtherNewsReaders.md)] and [[OtherUsefulStuff](OtherUsefulStuff.md)]

## Feed parsing ##
  * [libgrss](https://wiki.gnome.org/Libgrss) - C using GLib, does a little more than just parsing
  * [mRss](http://www.autistici.org/bakunin/libmrss/doc/) - plain C
  * [rss-glib](https://github.com/chergert/rss-glib/) - thin GObject wrapper of mrss, check if we can easily get this up to date?
  * [FeedReader](http://code.google.com/p/feed-reader-lib/) - C++
  * [feedparser](http://code.google.com/p/feedparser/) - Python, seems very complete and has a big test suite. Use for reference [source](http://code.google.com/p/feedparser/source/browse/feedparser/feedparser.py)
  * [SimplePie](http://simplepie.org/) - PHP
  * [System.ServiceModel.Syndication](https://github.com/mono/mono/tree/master/mcs/class/System.ServiceModel.Web/System.ServiceModel.Syndication) - Mono, implementation of [SyndactionFeed from .NET](http://msdn.microsoft.com/en-us/library/system.servicemodel.syndication.syndicationfeed.aspx)
## Converting RSS to Atom ##
  * [Comparison from intertwingly](http://www.intertwingly.net/wiki/pie/Rss20AndAtom10Compared)
  * ["Atomic RSS"](http://www.tbray.org/ongoing/When/200x/2005/07/27/Atomic-RSS)
  * [Feedomizer](https://github.com/zh/feedomizer) - RSS to Atom using Python feedparser
  * [Atom conversion tools](http://atom.geekhood.net/) - XSLTs from Atom to RSS

## XML ##
  * Started [Fido.Xml](https://gitorious.org/fido/fxml)
  * For writing, maybe port Mono's [XmlTextWriter2.cs](https://github.com/mono/mono/blob/master/mcs/class/System.XML/System.Xml/XmlTextWriter2.cs) (some utility functions in base class [XmlWiter.cs](https://github.com/mono/mono/blob/master/mcs/class/System.XML/System.Xml/XmlWriter.cs), also see [XmlWriterSettings.cs](https://github.com/mono/mono/blob/master/mcs/class/System.XML/System.Xml/XmlWriterSettings.cs)