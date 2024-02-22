import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

class Patient {
    private String name;
    private int age;
    private String gender;
    private String address;
    private String phoneNumber;
    
    public Patient(String name, int age, String gender, String address, String phoneNumber) {
        this.name = name;
        this.age = age;
        this.gender = gender;
        this.address = address;
        this.phoneNumber = phoneNumber;
    }
    
    public String getName() {
        return name;
    }
    
    public int getAge() {
        return age;
    }
    
    public String getGender() {
        return gender;
    }
    
    public String getAddress() {
        return address;
    }
    
    public String getPhoneNumber() {
        return phoneNumber;
    }
    
    @Override
    public String toString() {
        return "Name: " + name + ", Age: " + age + ", Gender: " + gender + ", Address: " + address + ", Phone Number: " + phoneNumber;
    }
}

class Hospital {
    private List<Patient> patients;
    
    public Hospital() {
        patients = new ArrayList<>();
    }
    
    public void addPatient(Patient patient) {
        patients.add(patient);
        System.out.println("Patient added successfully!");
    }
    
    public void displayPatients() {
        if (patients.isEmpty()) {
            System.out.println("No patients found.");
        } else {
            System.out.println("List of patients:");
            for (Patient patient : patients) {
                System.out.println(patient);
            }
        }
    }
}

public class HospitalManagementSystem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Hospital hospital = new Hospital();
        
        boolean exit = false;
        
        while (!exit) {
            System.out.println("Hospital Management System");
            System.out.println("1. Add Patient");
            System.out.println("2. Display Patients");
            System.out.println("3. Exit");
            System.out.print("Enter your choice: ");
            
            int choice = scanner.nextInt();
            scanner.nextLine(); // consume newline character
            
            switch (choice) {
                case 1:
                    System.out.print("Enter patient name: ");
                    String name = scanner.nextLine();
                    System.out.print("Enter patient age: ");
                    int age = scanner.nextInt();
                    scanner.nextLine(); // consume newline character
                    System.out.print("Enter patient gender: ");
                    String gender = scanner.nextLine();
                    System.out.print("Enter patient address: ");
                    String address = scanner.nextLine();
                    System.out.print("Enter patient phone number: ");
                    String phoneNumber = scanner.nextLine();
                    
                    Patient patient = new Patient(name, age, gender, address, phoneNumber);
                    hospital.addPatient(patient);
                    break;
                case 2:
                    hospital.displayPatients();
                    break;
                case 3:
                    exit = true;
                    break;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
            
            System.out.println();
        }
        
        scanner.close();
    }

{
    
}
}

