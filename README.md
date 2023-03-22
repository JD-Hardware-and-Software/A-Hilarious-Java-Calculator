import java.util.Scanner;

public class HilariousJavaCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Welcome to the Basic Calculator!");

        while (true) {
            System.out.println("Enter an operator (+, -, *, /) or 'q' to quit:");
            String operator = scanner.nextLine();

            if (operator.equals("q")) {
                System.out.println("Thanks for using the Basic Calculator!");
                break;
            }

            if (!operator.equals("+") && !operator.equals("-") && !operator.equals("*") && !operator.equals("/")) {
                System.out.println("Invalid operator. Please enter a valid operator.");
                continue;
            }

            System.out.println("Enter the first operand:");
            double operand1 = scanner.nextDouble();

            System.out.println("Enter the second operand:");
            double operand2 = scanner.nextDouble();

            double result;

            switch (operator) {
                case "+":
                    result = operand1 + operand2;
                    break;
                case "-":
                    result = operand1 - operand2;
                    break;
                case "*":
                    result = operand1 * operand2;
                    break;
                case "/":
                    if (operand2 == 0) {
                        System.out.println("Oops, you can't divide by zero!");
                        continue;
                    }
                    result = operand1 / operand2;
                    break;
                default:
                    result = 0;
            }

            System.out.println("Result: " + result);
        }

        scanner.close();
    }
}
