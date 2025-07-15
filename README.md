import java.util.Scanner;

public class CGPACalculator {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Step 1: Take input for the number of courses
        System.out.print("Enter number of courses: ");
        int numCourses = sc.nextInt();

        double totalGradePoints = 0;
        double totalCredits = 0;

        // Arrays to store grades and credits for displaying later
        double[] grades = new double[numCourses];
        double[] credits = new double[numCourses];

        // Step 2 & 3: Input grade and credit hours for each course and calculate total
        for (int i = 0; i < numCourses; i++) {
            System.out.print("Enter grade for course " + (i + 1) + ": ");
            grades[i] = sc.nextDouble();

            System.out.print("Enter credit hours for course " + (i + 1) + ": ");
            credits[i] = sc.nextDouble();

            totalGradePoints += grades[i] * credits[i];
            totalCredits += credits[i];
        }

        // Step 4: Compute CGPA
        double cgpa = totalGradePoints / totalCredits;

        // Step 5: Display individual course grades and final CGPA
        System.out.println("\n--- Course Grades ---");
        for (int i = 0; i < numCourses; i++) {
            System.out.println("Course " + (i + 1) + ": Grade = " + grades[i] + ", Credits = " + credits[i]);
        }

        System.out.printf("Final CGPA: %.2f\n", cgpa);

        sc.close();
    }
}
