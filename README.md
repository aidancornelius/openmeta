# OPENMETA
## Document management for OS X

**By Tom Andersen of ironic software**

Document management is finding and storing your documents. Traditionally document management is done with intrusive, large ‘systems’. The prices of these systems reflects their complexity.

For the small or not so small Mac based office, the current set of solutions is for the most part overkill.

We at Ironic Software have developed a system that is extensible, open sourced, and based on the OS X file system. Documents are not ‘stored’ in any special database, instead they are simply put where ever they make sense. A document management system must both store documents (which OpenMeta leaves up to the file system), and metadata about the files - meta data being tags, dates, ratings, people, etc associated with the document. OpenMeta uses the unix ‘extended attributes’ (latter) to store this metadata.

By storing both the files and the metadata on the file system, backing up and restoring a document management system can be done with (almost) any normal backup system. For some offices,
Time Machine will do more than an adequate job.

Storing metadata and files using no special formats or databases allows for very robust future proof behaviour. OpenMeta has been designed to last as long as OS X will last. There are no proprietary databases to deal with.

With all the data stored on the file system, there does need to be a search mechanism - the metadata as well as the contents of the documents need to be able to be searched. Apple already has a powerful search engine running on OS X - Spotlight. By running straight forward queries in Spotlight, metadata may be searched on a field by field basis. Spotlight also of course allows searching across all metadata at once. The default search application that ships with OS X - namely Spotlight.app will often not be an adequate tool for users to construct searches and deal with documents. Products like Ironic’s Deep are designed to offer a richer interface to document management than the simple Spotlight search UI.

### Details

Why Open Source
Open sourcing the ‘way’ to set metadata on a file in OS X allows for everyone to do it the same way, but just as important, sends a message to customers looking at an OpenMeta based system. That message being of course that us vendors will have much less ‘lock-in’ than with a wholly proprietary system. What is open source in OpenMeta is the formats, attribute names and conventions for metadata storage. Along with source code to store, retrieve and in some cases validate the information stored. OpenMeta in and of itself will not be a solution for anyone but the largest companies willing to do in house development of the tools and systems appropriate for their business.

Tools for the job
Ironic is releasing a simple command line tool openmeta, along with a simple OS X application called ‘Tagit’ (shown here) which allows users to tag and rate any file(s) on their system. Tacit also generates searches for files with ratings and tags as supplied in it’s search box.
In addition to these free utilities, Ironic has also shipped Deep - an image manager, and will soon be transitioning both Yep and Leap to OpenMeta. Deep uses OpenMeta to store tags and also to store colour information (palettes) about each image on a computer. In writing Deep we have developed the OpenMeta code to be able to handle the demands of a real commercial application.

Technical details.
The OpenMeta project is hosted at http://code.google.com/p/openmeta , at that site there is source code, a forum, a wiki, and more. A few points:
* OpenMeta uses no ‘secret’ Apple API.
* Indexing of Spotlight-able data is automatically handled by the OS.
* It is easy to add new metadata keys - these keys can be kept private for internal use, or registered in OpenMeta in order to build consensus. example: Workflows.
* Complex, solution specific binary data can also be stored.
* OpenMeta uses setxattr()/getxattr() to get and set all metadata.
* Because the metadata is not ‘inside the file’ it is easy to develop tools that allow metadata to be
included / excluded in a export. For example, when emailing a document, it may be desirable to not send along the private metadata that is set on the file.
* Access rights by users to files is fundamentally determined by file permissions on the server/ desktop/laptop that has the files resident on it. There are no other systems. If a user can log into a file system - then they can get at the files on it. Other document management solutions have their own built in access permissions system. While this can be useful, there are more times than not when this adds an unneeded layer of complexity.

The OpenMeta project is hosted at http://code.google.com/p/openmeta.

Ironic software’s web site is at http://www.ironicsoftware.com , and Tom Andersen can be reached at tom.andersen@gmail.com


**NOTE: This is just hosted here with a pod file, it’s not my software and I don’t provide support!**