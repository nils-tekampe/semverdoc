# Meaningful Manual Version Control Version 0.9.0
## Introduction
Keeping documents under automatic version control is not always possible or desired. Sometimes, it is unavoidable to implement version control of documents in a manual manner. 
This specification summaries an approach that has been widely used for many years. 

## Prerequisites
The following assumptions are taken in the rest of this document
1. A document is a digital representation of a written, drawn, presented, or memorialized representation of thought. (Adopted from  [wikipedia])
2. Documents are maintained on a computer system.
3. The computer systems supports the notion of [files] and folders. 
## Meaningful Manual Version Control (MMVC)
1. Each document under version control resides in a FOLDER. A folder may contain multiple documents under version control but the number of documents within a folder SHOULD be limited to limit the complexity. 
2. Each document name comprises the elements NAME\_VERSION\_.EXTENSION. The elements of the document name are separate by the use of the underscore ([ASCII] Code 95)
3. The NAME part of the document SHALL uniquely identify the document within the folder. 
4. The VERSION part of the filename SHALL follow the semantic versioning scheme. The VERSION part may be headed by the letter „V“ in order to indicate the following version information. 
5. The .EXTENSION part of the filename may also be empty. 
6. Each folder also contains a subfolder named „old“ that stores previous versions of the documents. 
7. At any time, FOLDER SHALL only contain the latest version of a document. All preceding versions SHALL reside within the „old“ folder. 
8. Creating a new version of a DOCUMENT SHALL follow the following process:
	9.  A copy of DOCUMENT is created within FOLDER. 
	10. The VERSION part of the filename of the copy of the document is incremented according to the semantic versioning specification
	11. DOCUMENT is moved to the „old“ folder. 

## Example
The following shows a typical example of a folder structure that develops when using MMVC. 
'''
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
  '''
