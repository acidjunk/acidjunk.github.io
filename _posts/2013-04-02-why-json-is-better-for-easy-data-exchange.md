---
id: 790
title: Why json is better for easy data exchange
date: 2013-04-02T05:15:40+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=790
permalink: /2013/04/why-json-is-better-for-easy-data-exchange/
categories:
  - Computerz
---
### <span style="font-size: 1.17em;">JSON: The Fat-Free Alternative to XML</span>

Extensible Markup Language (XML) is a text format derived from Standard Generalized Markup Language (SGML). Compared to SGML, XML is simple. HyperText Markup Language (HTML), by comparison, is even simpler. Even so, a good reference book on HTML is an inch thick. This is because the formatting and structuring of documents is a complicated business.

Most of the excitement around XML is around a new role as an interchangeable data serialization format. XML provides two enormous advantages as a data representation language:

It&#8217;s text-based. It&#8217;s position-independent. These together encouraged a higher level of application-independence than other data-interchange formats. The fact that XML was already a W3C standard meant that there wasn&#8217;t much left to fight about (or so it seemed).

Unfortunately, XML is not well suited to data-interchange and it doesn&#8217;t match the data model of most programming languages. When most programmers saw XML for the first time, they were shocked at how ugly and inefficient it was. The XML tags generate quite some overhead. There is another text notation that has all of the advantages of XML, but is much better suited to data-interchange. That notation is JavaScript Object Notation (JSON).

JSON promises the same benefits of interoperability and openness, but without the disadvantages.

Let&#8217;s compare XML and JSON on the attributes that the XML community considers important.

**Simple to use**

JSON is much simpler than XML. JSON has a much smaller grammar and maps more directly onto the data structures used in modern programming languages.

**Extensible**

JSON is not extensible because it does not need to be. JSON is not a document markup language, so it is not necessary to define new tags or attributes to represent data in it.

**Interoperable**

JSON has the same interoperability potential as XML.

**Openness**

JSON is at least as open as XML, perhaps more so because it is not in the center of corporate/political standardization struggles.

### In summary these are some of the advantages of XML

XML separates the presentation of data from the structure of that data.

XML requires translating the structure of the data into a document structure. This mapping can be complicated. JSON structures are based on arrays and records. That is what data is made of. XML structures are based on elements (which can be nested), attributes (which cannot), raw content text, entities, DTDs, and other meta structures.

JSON is a better _data exchange format_. XML is a better _document exchange format_.

Use the right tool for the right job.

## When to use XML

In general, XML is good for situations in which&#8230;

  * You need message validation
  * You&#8217;re using XSLT
  * Your messages include a lot of marked-up text
  * You need to interoperate with environments that don&#8217;t support JSON
  * You need attributes or namespacing

## When to use Json

In general, XML is good for situations in which&#8230;

  * Messages don&#8217;t need to be validated, or validating their deserialization is simple
  * You&#8217;re not transforming messages, or transforming their deserialization is simple
  * Your messages are mostly data, not marked-up text
  * The messaging endpoints have good JSON tools