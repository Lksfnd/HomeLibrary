# HomeLibary

## General Idea
The idea is a web-based application that allows users to upload their E-Books (any format like PDF, Mobi)  
and assign them metadata. Afterwards users should be able to serach for books based on Author, ISBN, etc.  
An additional feature to load image Covers and Metadata automatically would be an advantage as well.  

## Programming Language
Generally there are two options: Full PHP applications or JavaScript. The advantage of javascript is that  
its way easiert to manipulate data within the page and makes it more dynamic. PHP however has the advantage  
of not requiring as much work and not needing a seperate server.  
This project will be written in JavaScript (Client) using a Rest-Service (PHP) to dynamicly add data (like search autocompletion).

## Database
Obviously for this project, a relational database is the best choice here. MySQL will be used. The database Structure is described
at the bottom of this page.  

## The Features

### UI
The UI should be simple to use and good-looking. First goal will be to create a working book-management system that allows  
the upload of ebooks and manually tag them. The next step will be an automated completion of metadata via any book api.  
Afterwards, a user-login system could be added to make personal "playlist-style" lists to keep track of the books read.  
Since Amazon allows the users to send ebooks directly to their kindle using an email adress, that would be from advantage as well.  


## Database - ERM
NN -> Not Null  
AI -> Auto Insert  
UN -> Unique  
PK, FK -> Primary and Foreighn Key  
```javscript
Book {  
    PK id: uint AI NN           ** The identifier for the book  
    title: text NN              ** The name of the book  
    FK author: uint NN          ** The ID of the author  
    description: string         ** The book description  
    isbn: string UN             ** The ISBN of the book  
    cover: string               ** A path to the cover of the book   
    releasedate: date           ** Release date of the book  
    uploadDate: date            ** Date when the book was added to the libary  
    tags: string                ** List of tags assigned to the book  
    pages: uint                 ** Number of pages  
    FK publisher: uint          ** The publisher's id  
}  
  
Author {  
    PK id: uint AI NN           ** The identifier for the autor  
    name: text NN               ** The name of the autor  
    tagList: string             ** Connected to Tag-Table (not opimal, but way easier), best case would be assistant-table  
    bio: string                 ** Optional biography of the author (HTML should be allowed?)  
}  
  
Publisher {  
    PK id: uint AI NN           ** The identifier for the publisher  
    name: string NN             ** The title of the publisher  
}  
  
Tag {  
    PK id: uint AI NN           ** The identifier for the tag  
    title: text NN              ** The name of the tag  
}  
```
## Contributing
*Following soon*

### General Stuff for coders
Here's some information about the recommended (my) dev-setup.  
MySQL:  
    name: root  
    pass: 1234