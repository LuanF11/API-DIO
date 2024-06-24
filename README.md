# API-DIO

classDiagram
    direction LR

    class LibraryApplication {
    }

    class BookController {
        +List~Book~ getAllBooks()
        +ResponseEntity~Book~ getBookById(Long id)
        +Book createBook(Book book)
        +ResponseEntity~Book~ updateBook(Long id, Book bookDetails)
        +ResponseEntity~Void~ deleteBook(Long id)
    }

    class BookService {
        -BookRepository bookRepository
        +List~Book~ getAllBooks()
        +Optional~Book~ getBookById(Long id)
        +Book saveBook(Book book)
        +void deleteBook(Long id)
    }

    class BookRepository {
    }

    class Book {
        +Long id
        +String title
        +String author
        +String isbn
        +Long getId()
        +void setId(Long id)
        +String getTitle()
        +void setTitle(String title)
        +String getAuthor()
        +void setAuthor(String author)
        +String getIsbn()
        +void setIsbn(String isbn)
    }

    LibraryApplication --> BookController
    BookController --> BookService
    BookService --> BookRepository
    BookRepository --> Book
