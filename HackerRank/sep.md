## Day-1
### Java Date and Time
```java
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;
import java.time.DayOfWeek;
import java.util.Scanner;

public class DayOfWeekFinder {
    public static void main(String[] args) {
        // Read input
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();
        scanner.close();
        
        // Define the date format
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("MM dd yyyy");
        
        // Parse the input
        LocalDate date = LocalDate.parse(input, formatter);
        
        // Get the day of the week
        DayOfWeek dayOfWeek = date.getDayOfWeek();
        
        // Print the day of the week in uppercase
        System.out.println(dayOfWeek.name());
    }
}

```
###
