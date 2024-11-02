import java.util.ArrayList;
import java.util.Scanner;

public class StudentGradeTracker {

    // Method to calculate the average grade
    public static double calculateAverage(ArrayList<Double> grades) {
        double sum = 0;
        for (double grade : grades) {
            sum += grade;
        }
        return sum / grades.size();
    }

    // Method to convert numerical average to letter grade
    public static String getLetterGrade(double average) {
        if (average >= 90) {
            return "A";
        } else if (average >= 80) {
            return "B";
        } else if (average >= 70) {
            return "C";
        } else if (average >= 60) {
            return "D";
        } else {
            return "F";
        }
    }

    // Method to calculate GPA from the average grade
    public static double calculateGPA(double average) {
        if (average >= 90) {
            return 4.0;
        } else if (average >= 80) {
            return 3.0;
        } else if (average >= 70) {
            return 2.0;
        } else if (average >= 60) {
            return 1.0;
        } else {
            return 0.0;
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ArrayList<Double> grades = new ArrayList<>();
        
        // Prompt the user for grades
        System.out.println("Enter grades for different subjects or assignments (type -1 to finish):");

        while (true) {
            System.out.print("Enter grade: ");
            double grade = scanner.nextDouble();
            if (grade == -1) {
                break;  // Exit the loop when user enters -1
            }
            grades.add(grade);
        }

        // Calculate the average grade
        if (!grades.isEmpty()) {
            double average = calculateAverage(grades);
            String letterGrade = getLetterGrade(average);
            double gpa = calculateGPA(average);

            // Display the results
            System.out.println("\nAverage Grade: " + average);
            System.out.println("Letter Grade: " + letterGrade);
            System.out.println("GPA: " + gpa);
        } else {
            System.out.println("No grades were entered.");
        }
    }
