import java.util.HashMap;
import java.util.Scanner;
public class RomanToIntegerWithUserInput {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 System.out.print("Enter a Roman numeral: ");
 String romanNumeral = scanner.nextLine().toUpperCase(); // Convert to uppercase for caseinsensitivity
 int result = romanToInteger(romanNumeral);
 System.out.println("The integer value of " + romanNumeral + " is: " + result);
 }
 public static int romanToInteger(String s) {
 // Create a HashMap to store the values of Roman numerals
 HashMap<Character, Integer> romanValues = new HashMap<>();
 romanValues.put('I', 1);
 romanValues.put('V', 5);
 romanValues.put('X', 10);
 romanValues.put('L', 50);
 romanValues.put('C', 100);
 romanValues.put('D', 500);
 romanValues.put('M', 1000);
 int result = 0;
 int prevValue = 0;
 // Iterate through the Roman numeral string from right to left
 for (int i = s.length() - 1; i >= 0; i--) {
 int curValue = romanValues.get(s.charAt(i));
 // If the current value is less than the previous value, subtract it
 if (curValue < prevValue) {
 result -= curValue;
 }
else {
 result += curValue;
 }
 prevValue = curValue;
 }
 return result;
 }
}