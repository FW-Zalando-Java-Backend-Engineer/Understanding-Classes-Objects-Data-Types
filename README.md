# 🎯 Understanding Classes, Objects & Data Types  

## 📌 **Overview**  
This assignment will help you understand how to:  
- Create **Java classes** and work with **objects**  
- Differentiate between **instance** and **static methods**  
- Use **primitive & reference data types**  
- Work with **arrays** of objects (Optional!) 

Each task builds upon the previous one, reinforcing key Java concepts.

---

## **🚀 Task 1: Creating a Simple Class**  

### **📝 Task Description**  
You will create a `Book` class with properties, a constructor, and a method to display book details.

### **📍 Steps to Complete:**  
1. **Create a new file `Book.java`** in your project.  
2. Define the following instance variables (fields):  
   ```java
   String title;
   String author;
   int pages;
   boolean isAvailable;
   ```
3. Create a **constructor** to initialize all fields:
   ```java
   public Book(String title, String author, int pages, boolean isAvailable) {
       this.title = title;
       this.author = author;
       this.pages = pages;
       this.isAvailable = isAvailable;
   }
   ```
4. Add a method `printBookInfo()` to display book details:
   ```java
   public void printBookInfo() {
       System.out.println("Title: " + title);
       System.out.println("Author: " + author);
       System.out.println("Pages: " + pages);
       System.out.println("Available: " + isAvailable);
       System.out.println();
   }
   ```
5. **Create a `Main.java` file**, instantiate two `Book` objects, and call `printBookInfo()`:
   ```java
   public class Main {
       public static void main(String[] args) {
           Book book1 = new Book("Clean Code", "Robert C. Martin", 464, true);
           Book book2 = new Book("The Pragmatic Programmer", "Andy Hunt", 320, false);

           book1.printBookInfo();
           book2.printBookInfo();
       }
   }
   ```
6. **Run the program**, and ensure it prints book details correctly.  

### **📚 References**
- Java Classes & Objects: [Oracle Docs](https://docs.oracle.com/javase/tutorial/java/concepts/class.html)
- Java Object-Oriented Programming: [W3Schools](https://www.w3schools.com/java/java_oop.asp)

---

## **🚀 Task 2: Adding Static Variables & Methods**  

### **📝 Task Description**  
This task will teach you the difference between **instance variables** and **static variables**.

### **📍 Steps to Complete:**  
1. **Modify the `Book` class** by adding a static variable `totalBooks`:  
   ```java
   static int totalBooks = 0;
   ```
2. Update the constructor to increment `totalBooks` each time a new `Book` is created:  
   ```java
   public Book(String title, String author, int pages, boolean isAvailable) {
       this.title = title;
       this.author = author;
       this.pages = pages;
       this.isAvailable = isAvailable;
       totalBooks++;  // Increment static variable
   }
   ```
3. Add an **instance method** `isThickBook()` to check if the book has more than 300 pages:  
   ```java
   public boolean isThickBook() {
       return pages > 300;
   }
   ```
4. Modify `Main.java` to:  
   - Create **three** `Book` objects  
   - Print `totalBooks` using `Book.totalBooks`  
   - Use `isThickBook()` to check each book  
   ```java
   public class Main {
       public static void main(String[] args) {
           Book book1 = new Book("Clean Code", "Robert C. Martin", 464, true);
           Book book2 = new Book("The Pragmatic Programmer", "Andy Hunt", 320, false);
           Book book3 = new Book("Java: The Complete Reference", "Herbert Schildt", 1256, true);

           book1.printBookInfo();
           book2.printBookInfo();
           book3.printBookInfo();

           System.out.println("Total books created: " + Book.totalBooks);

           System.out.println("Is " + book1.title + " a thick book? " + book1.isThickBook());
           System.out.println("Is " + book2.title + " a thick book? " + book2.isThickBook());
           System.out.println("Is " + book3.title + " a thick book? " + book3.isThickBook());
       }
   }
   ```
5. **Run the program** and verify the output.

### **📚 References**
- Static vs. Instance Variables: [Oracle Docs](https://docs.oracle.com/javase/tutorial/java/javaOO/classvars.html)
- Static Methods in Java: [GeeksForGeeks](https://www.geeksforgeeks.org/static-methods-vs-instance-methods-java)

---

## **🚀 Bonus Challenge (Optional!) : Storing Objects in Arrays **  

### **📝 Task Description**  
You will work with **arrays of objects** and write a method to find the book with the most pages.

### **📍 Steps to Complete:**  
1. Modify `Main.java` to **create an array** of `Book` objects:
   ```java
   public class Main {
       public static void main(String[] args) {
           Book[] books = {
               new Book("Clean Code", "Robert C. Martin", 464, true),
               new Book("The Pragmatic Programmer", "Andy Hunt", 320, false),
               new Book("Java: The Complete Reference", "Herbert Schildt", 1256, true),
               new Book("Effective Java", "Joshua Bloch", 416, true),
               new Book("Design Patterns", "Erich Gamma", 395, false)
           };

           Book longestBook = findLongestBook(books);
           System.out.println("The longest book is: " + longestBook.title);
       }
   }
   ```
2. **Create a method `findLongestBook(Book[] books)`** that returns the book with the most pages:
   ```java
   public static Book findLongestBook(Book[] books) {
       Book longest = books[0];  // Assume the first book is the longest
       for (Book book : books) {
           if (book.pages > longest.pages) {
               longest = book;
           }
       }
       return longest;
   }
   ```
3. **Run the program**, ensuring it correctly finds and prints the longest book.

### **📚 References**
- Java Arrays (Oracle Docs): [Oracle Docs: Java Arrays](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html)
- Working with Arrays in Java: [Arrays in Java](https://www.geeksforgeeks.org/arrays-in-java/)

---

## **📜 Expected Output Example**  
```
Title: Clean Code
Author: Robert C. Martin
Pages: 464
Available: true

Title: The Pragmatic Programmer
Author: Andy Hunt
Pages: 320
Available: false

Title: Java: The Complete Reference
Author: Herbert Schildt
Pages: 1256
Available: true

Total books created: 3

Is Clean Code a thick book? true
Is The Pragmatic Programmer a thick book? true
Is Java: The Complete Reference a thick book? true

The longest book is: Java: The Complete Reference
```

---

## 📌 **Submission Instructions**
1. **Clone the GitHub Classroom Repository** provided by your instructor.  
2. Push your completed Java files (`Book.java` & `Main.java`) to your repository.  
3. Submit the GitHub link.

---

