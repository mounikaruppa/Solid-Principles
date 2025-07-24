Add those 5 principles code here! in this folder

//SingleResponsibilityPrinciple.java

class Movie {
    String title;
    String hero;

    Movie(String title, String hero) {
        this.title = title;
        this.hero = hero;
    }
}

class MoviePrinter {
    void printMovie(Movie movie) {
        System.out.println("Movie Title: " + movie.title);
        System.out.println("Hero: " + movie.hero);
    }
}

public class SingleResponsibilityPrinciple {
    public static void main(String[] args) {
        Movie m = new Movie("Hari Hara Veera Mallu", "Powerstar Pawan Kalyan");
        MoviePrinter printer = new MoviePrinter();
        printer.printMovie(m);
    }
}




//opencloseprinciple.java

class HPCharacter {
    void describe() {
        System.out.println("This is a character from Harry Potter.");
    }
}

class HarryPotter extends HPCharacter {
    void describe() {
        System.out.println("Harry Potter is the brave chosen one.");
    }
}

class RonWeasley extends HPCharacter {
    void describe() {
        System.out.println("Ron Weasley is Harry's loyal best friend.");
    }
}

class HermioneGranger extends HPCharacter {
    void describe() {
        System.out.println("Hermione Granger is smart and loves books.");
    }
}

class Dobby extends HPCharacter {
    void describe() {
        System.out.println("Dobby is a kind and free house-elf.");
    }
}

public class OpenClosedPrinciple {
    public static void main(String[] args) {
        HPCharacter harry = new HarryPotter();
        HPCharacter ron = new RonWeasley();
        HPCharacter hermione = new HermioneGranger();
        HPCharacter dobby = new Dobby();

        harry.describe();
        ron.describe();
        hermione.describe();
        dobby.describe();
    }
}



//LiskovSubstitutionPrinciple.java


class Drama {
    void play() {
        System.out.println("Playing a drama...");
    }
}

// Chinese Drama subclass
class CDrama extends Drama {
    void play() {
        System.out.println("Playing Chinese drama: Hidden Love");
    }
}

// Korean Drama subclass
class KDrama extends Drama {
    void play() {
        System.out.println("Playing Korean drama: Queen of Tears");
    }
}

public class LiskovPrinciple {
    public static void main(String[] args) {
        Drama cdrama = new CDrama();
        Drama kdrama = new KDrama();
        cdrama.play();
        kdrama.play();
    }
}



//InterfaceSegregationPrinciple.java

interface CanRun {
    void run();
}

interface CanPrank {
    void prank();
}


class Heidi implements CanRun {
    public void run() {
        System.out.println("Heidi is happily running through the mountains!");
    }
}


class Shinchan implements CanPrank {
    public void prank() {
        System.out.println("Shinchan is playing a prank on his dad!");
    }
}

// Main class
public class InversionPrinciple {
    public static void main(String[] args) {
        Heidi heidi = new Heidi();
        Shinchan shinchan = new Shinchan();

        heidi.run();
        shinchan.prank();
    }
}


//DependencyInversionPrinciple.java

interface Book {
    void read();
}

// Concrete class: Verity

class Verity implements Book {
    public void read() {
        System.out.println("Reading: Verity by Colleen Hoover.");
    }
}

// Concrete class: It Ends With Us

class ItEndsWithUs implements Book {
    public void read() {
        System.out.println("Reading: It Ends With Us by Colleen Hoover.");
    }
}

class Reader {
    private Book book;

    public Reader(Book book) {
        this.book = book;
    }

    public void startReading() {
        book.read();
    }
}

// Main class 
public class DependencyInversionPrinciple {
    public static void main(String[] args) {
        Book book1 = new Verity();
        Book book2 = new ItEndsWithUs();

        Reader reader1 = new Reader(book1);
        Reader reader2 = new Reader(book2);

        reader1.startReading();
        reader2.startReading();
    }
}



