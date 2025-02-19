# Extendedcalculator
class InvalidInputException extends Exception {
public InvalidInputException(String message) {
super(message);
}
}
class NegativeNumberException extends Exception {
public NegativeNumberException(String message) {
super(message);
}
}
class InvalidOperatorException extends Exception {
public InvalidOperatorException(String message) {
super(message);
}
}
class UnsupportedOperationException extends Exception {
public UnsupportedOperationException(String message) {
super(message);
}
}
class Calculator {
public static double performOperation(double num1, double num2, char operator)
throws InvalidInputException, NegativeNumberException,
InvalidOperatorException, UnsupportedOperationException {
if (num1< 0 || num2< 0) {
    throw new NegativeNumberException("Negative numbers are not allowed.");
}
switch (operator) {
case'+':
return num1 + num2;
case'-':
return num1 - num2;
case'*':
return num1 * num2;
case'/':
if (num2 == 0) {
throw new UnsupportedOperationException("Cannot divide by zero.");
}
return num1 / num2;
default:
throw new InvalidOperatorException("Invalid operator:" + operator);
}
}
}

public class ExtendedCalculator {
   public static void main(String[] args) {
try {
double result1 = Calculator.performOperation(10,2,'+');
System.out.println("Result 1:" + result1);
double result2 = Calculator.performOperation(8,0,'-');
System.out.println("Result 2:"+ result2); // This line won&#39;t be reached
} catch (InvalidInputException | NegativeNumberException |
InvalidOperatorException | UnsupportedOperationException e) {
System.out.println("Exception:"+ e.getMessage());
}
    }
}
Output
 Result 1:12.0
Result 2:8.0

