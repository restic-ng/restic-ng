About restic-ng
---------------

restic-ng is a fork of restic aiming to add some specific features that have shown to be time-intensive to fix.
Most of these features have been discussed in restic issues and require changes in the repository format.
As a result restic-ng's repositories will not be compatible with restic repositories. It is however indented to make changes to the repository format in a way that restic repositories can be transformed to restic-ng repositories without much effort.

The current goal of restic-ng is only to build a restic-based backup tool with the added features. Any other features, bug fixes for bugs within restic etc. are **not** in current the scope of restic-ng.

Once the goals of restic-ng are reached, we will decide on the future of restic-ng.

Goals
-----

The goals of restic-ng are:

1. Add compression
2. Support large-scale repositories (many snapshots, many files, large files)
3. Drop memory consumption
4. Add possibilities to "import" a restic repository, i.e. to modify a restic repository such that it becomes a restic-ng repository
5. Add asymmetric encryption
6. Add locking-free operation
7. Add possibility to choose crypto, compression, hashing algorithms 

To Do
-----

List of next steps:

-  [ ] Add compression

  - [ ] add length and compression type to index  
  - [ ] update index docu in design document
  - [ ] add compression to save functions for blobs
  - [ ] add compression to read functions for blobs
  - [ ] add compression to save functions for files
  - [ ] add compression to read functions for files

- [ ] Large-scale-repositories 

  - [ ] support many snapshots - make snapshot a blob
  
    - [ ] update design document
    - [ ] add new snapshot blob type
    - [ ] change snapshot load functions
    - [ ] change list functions
    - [ ] change write function

- [ ] Lower memory consumtion

  - [ ] refactor index data structure

- [ ] Add possibilities to "import" a restic repository

  - [ ] add import command

- [ ] Add asymmetric encryption

  - [ ] Add key blobs
  
    - [ ] update design document
    - [ ] add new key blob type
    - [ ] implement save functionality
    - [ ] implement load functionality
    
  - [ ] Add key-per-blob  
  
    - [ ] update design document
    - [ ] add key to index
    - [ ] add key functionality to save functions for blobs
    - [ ] add key functionality to read functions for blobs
    - [ ] add key functionality to save functions for files
    - [ ] add key functionality to read functions for files
    
  - [ ] Refactor key management

- [ ] Add lock-free operation

  - [ ] Create tomb data structure in repository
  
    - [ ] update design document
    - [ ] add write tomb functionality
    - [ ] add read tomb functionality
    
  - [ ] Update read functions
  
    - [ ] delete tomb when reading data already in tomb
    
  - [ ] Update delete functions
  
    - [ ] implement delete request (put into tomb) functionality
    - [ ] implement final delete functionality
    - [ ] implement delete process 

- [ ] Add possibility to choose crypto, compression, hashing algorithms 

  - [ ] Data structure
  
    - [ ] update design document
    - [ ] add information to index
    - [ ] store default values in config
    - [ ] make interfaces 
    - [ ] replace existing code to use the interfaces
    - [ ] add alternative implementations for crypto, compression, hashing
