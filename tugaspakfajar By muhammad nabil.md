```dart
void main() {
  Library library = Library();

  // Menambahkan buku ke perpustakaan
  library.addBook(Book('The Catcher in the Rye', 'J.D. Salinger'));
  library.addBook(Book('To Kill a Mockingbird', 'Harper Lee'));
  library.addBook(Book('1984', 'George Orwell'));

  // Menampilkan daftar buku
  library.displayBooks();

  // Meminjam buku
  library.borrowBook('1984');

  // Menampilkan daftar buku setelah peminjaman
  library.displayBooks();

  // Mengembalikan buku
  library.returnBook('1984');

  // Menampilkan daftar buku setelah pengembalian
  library.displayBooks();

  // Contoh penggunaan anonymous function dan closure
  var addBooks = library.makeAdder(2);
  print('Total books after addition: ${addBooks(3)}');
}

class Book {
  String title;
  String author;
  bool isBorrowed;

  Book(this.title, this.author, {this.isBorrowed = false});
}

class Library {
  List<Book> books = [];

  // Menambahkan buku ke perpustakaan
  void addBook(Book book) {
    books.add(book);
    print('Book added: ${book.title}');
  }

  // Meminjam buku
  void borrowBook(String title) {
    for (var book in books) {
      if (book.title == title && !book.isBorrowed) {
        book.isBorrowed = true;
        print('Book borrowed: $title');
        return;
      }
    }
    print('Book not available: $title');
  }

  // Mengembalikan buku
  void returnBook(String title) {
    for (var book in books) {
      if (book.title == title && book.isBorrowed) {
        book.isBorrowed = false;
        print('Book returned: $title');
        return;
      }
    }
    print('Book not found: $title');
  }

  // Menampilkan daftar buku
  void displayBooks() {
    print('Available books:');
    for (var book in books) {
      if (!book.isBorrowed) {
        print('${book.title} by ${book.author}');
      }
    }
    print('Borrowed books:');
    for (var book in books) {
      if (book.isBorrowed) {
        print('${book.title} by ${book.author}');
      }
    }
  }

  // Fungsi untuk closure
  Function makeAdder(int addBy) {
    return (int i) => addBy + i;
  }
}

// Function Parameter & Function Opsional
void greet(String name, [String? message]) {
  if (message != null) {
    print('Hello, $name! $message');
  } else {
    print('Hello, $name!');
  }
}

// Inner Function, Function Return Value, Function Short Expression
int add(int a, int b) => a + b; // Short expression

void innerFunctionExample() {
  int multiply(int x, int y) {
    return x * y;
  }

  int result = multiply(3, 4);
  print('Result of inner function: $result');
}

// Anonymous Function & Scope
void anonymousFunctionExample() {
  var list = [1, 2, 3, 4];

  list.forEach((item) {
    print('Item: $item');
  });
}

void scopeExample() {
  int outerVariable = 10;

  void innerFunction() {
    int innerVariable = 20;
    print('Outer Variable: $outerVariable');
    print('Inner Variable: $innerVariable');
  }

  innerFunction();
}
```