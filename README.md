import java.util.Scanner;

public class StudentGradeTracker {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of students: ");
        int n = sc.nextInt();

        String[] names = new String[n];
        int[] marks = new int[n];

        int total = 0;
        int highest = -1, lowest = 101;
        String topStudent = "", lowStudent = "";

        for (int i = 0; i < n; i++) {
            System.out.print("Enter Student Name: ");
            names[i] = sc.next();

            System.out.print("Enter Marks: ");
            marks[i] = sc.nextInt();

            total += marks[i];

            if (marks[i] > highest) {
                highest = marks[i];
                topStudent = names[i];
            }

            if (marks[i] < lowest) {
                lowest = marks[i];
                lowStudent = names[i];
            }
        }

        double average = (double) total / n;

        System.out.println("\n----- Student Report -----");
        for (int i = 0; i < n; i++) {
            System.out.println(names[i] + " : " + marks[i]);
        }

        System.out.println("Average Marks : " + average);
        System.out.println("Highest Marks : " + highest + " (" + topStudent + ")");
        System.out.println("Lowest Marks : " + lowest + " (" + lowStudent + ")");

        sc.close();
    }
}
