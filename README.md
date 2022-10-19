# Configuration File System

This is an idea for a data access protocol that I would like to implement. It is aimed at comprehensive configuration of software. I don't really like the way that languages such as JSON and XML work. XML requires that you want a tree and JSON has a bunch of syntax burden. I want to abstract the data into something more similar to a file system, where the data elements are type agnostic. All data stored will be stored as if it were simply a stream of bytes and accessed using a kind of path. The user will be able to set a "CWD" or access data directly using a string which is a fully qualified name. The routine accessing the data needs to know what to make of it and how to structure it for use. The data is serialzied in a format that is similar to a file system with a name table and pointers into sectors of data that could be fragmented if it does not fit into a sector. All of the API routines will memic the stdlib C routines that access file system streams. 

## Implemented features
* create and delete data
* open/close/read/write interface
* open mode of R/W/A/RW
* paths to data given by a string
* notion of a "current working directory" (CWD)
* globbing and traversing
* wild cards
* serialization
* serialization modes
  * immediate
  * cached

## Unimplemented features
* file access time 
* user permissions
* journaling
* error detection/correction
