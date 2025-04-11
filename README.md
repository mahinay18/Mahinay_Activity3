# Mahinay_Activity3
import java.util.Scanner;

public class StudentSort {

    static class Student {
        String name;
        double grade;

        public Student(String name, double grade) {
            this.name = name;
            this.grade = grade;
        }

        public String toString() {
            return name + " - " + grade;
        }
    }

    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);

        System.out.print("How many students? ");
        int numStudents = s.nextInt();
        s.nextLine();  

        Student[] Students = new Student[numStudents];
        for (int i = 0; i < numStudents; i++) {
            System.out.println("\nEnter details for student " + (i + 1));
            System.out.print("Name: ");
            String name = s.nextLine();

            System.out.print("Grade: ");
            double grade = s.nextDouble();
            s.nextLine();  
            Students[i] = new Student(name, grade);
        }

        bubbleSort(Students);

        System.out.println("\nSorted Students (Ascending):");
        for (Student st : Students) {
            System.out.println(st);  
        }
    }

    public static void bubbleSort(Student[] arr) {
        int n = arr.length;  
        boolean swapped;

        for (int i = 0; i < n - 1; i++) {  
            swapped = false;

            for (int j = 0; j < n - i - 1; j++) {  
                if (arr[j].grade > arr[j + 1].grade) {  
                    Student temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    swapped = true;
                }
            }

    
            if (!swapped) break;
        }
    }
}
