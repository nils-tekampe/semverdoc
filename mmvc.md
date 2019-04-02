Meaningful Manual Version Control Version 1.1.0
================================================
Keeping documents under automatic version control is not always possible or desired. Sometimes, it is unavoidable to implement version control of documents in a manual manner. 
This specification summaries an approach that has been widely used for many years. 

Prerequisites
-------------
The following assumptions are taken in the rest of this document
1. A document is a digital representation of a written, drawn, presented, or memorialized representation of thought. (Adopted from  [wikipedia](https://en.wikipedia.org/wiki/Document))
1. Documents are maintained on a computer system.
1. The computer systems supports the notion of [files](https://en.wikipedia.org/wiki/Computer_file) and folders. 
1. Documents are kept on the computer system in form of files.

Meaningful Manual Version Control (MMVC)
----------------------------------------

1. Each document under version control is represented by a FILE that resides in a FOLDER. A folder may contain multiple documents under version control but the number of documents within a folder SHOULD be limited to limit the complexity. 
1. Each FILE name comprises the elements NAME\_VERSION.EXTENSION. The elements of the FILE name are separate by the use of the underscore ([ASCII](https://en.wikipedia.org/wiki/ASCII) Code 95)
1. The NAME part of the FILE SHALL uniquely identify the document within the folder. 
1. The VERSION part of the filename SHALL follow the semantic versioning scheme. The VERSION part may be headed by the letter „V“ in order to indicate the following version information. 
1. The .EXTENSION part of the filename may also be empty. 
1. Each FOLDER also contains a subfolder named „old“ that stores previous versions of the documents. 
1. At any time, FOLDER SHALL only contain the latest version of a document. All preceding versions SHALL reside within the „old“ folder. 
1. The "old" folder SHALL ONLY be used to store superseeded versions of documents. 
1. Creating a new version of a DOCUMENT SHALL follow the following process:
	1.  A copy of DOCUMENT is created within FOLDER. 
	1. The VERSION part of the filename of the copy of the document is incremented according to the semantic versioning specification.
	1. DOCUMENT is moved to the „old“ folder. 

Example
-------
The following shows a typical example of a folder structure that develops when using MMVC. 
```
.
└── Documentation
	├── comments_V1.0.0.doc
	├── old
	│   ├── comments_V0.9.0.doc
	│   ├── comments_V0.9.5.doc
	│   ├── specification_V0.0.1.txt
	│   ├── specification_V0.1.1.txt
	│   ├── specification_V1.0.0.txt
	│   └── specification_V9.0.0.txt
	└── specification_V1.0.1.txt
  ```
License
-------
Creative Commons - CC BY 3.0 
http://creativecommons.org/licenses/by/3.0/
