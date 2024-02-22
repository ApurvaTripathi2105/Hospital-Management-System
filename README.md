import java.util.ArrayList;
import java.util.Scanner;

class Patient {
    private String name;
    private int age;
    private String gender;
    private String address;

    public Patient(String name, int age, String gender, String address) {
        this.name = name;
        this.age = age;
        this.gender = gender;
        this.address = address;
    }

    // Getters and setters for the Patient class
}

class Doctor {
    private String name;
    private String specialization;

    public Doctor(String name, String specialization) {
        this.name = name;
        this.specialization = specialization;
    }

    // Getters and setters for the Doctor class
}

class Appointment {
    private Patient patient;
    private Doctor doctor;
    private String date;

    public Appointment(Patient patient, Doctor doctor, String date) {
        this.patient = patient;
        this.doctor = doctor;
        this.date = date;
    }

    // Getters and setters for the Appointment class
}

class Hospital {
    private ArrayList<Patient> patients;
    private ArrayList<Doctor> doctors;
    private ArrayList<Appointment> appointments;

    public Hospital() {
        this.patients = new ArrayList<>();
        this.doctors = new ArrayList<>();
        this.appointments = new ArrayList<>();
    }

    // Methods to add and retrieve patients, doctors, and appointments

    public void addPatient(Patient patient) {
        this.patients.add(patient);
    }

    public void addDoctor(Doctor doctor) {
        this.doctors.add(doctor);
    }

    public void scheduleAppointment(Patient patient, Doctor doctor, String date) {
        Appointment appointment = new Appointment(patient, doctor, date);
        this.appointments.add(appointment);
    }

    // Other methods for searching patients, doctors, and appointments

    public ArrayList<Patient> getPatients() {
        return this.patients;
    }

    public ArrayList<Doctor> getDoctors() {
        return this.doctors;
    }

    public ArrayList<Appointment> getAppointments() {
        return this.appointments;
    }
}

public class HospitalManagementSystem {
    public static void main(String[] args) {
        Hospital hospital = new Hospital();

        // Add sample patients and doctors
        hospital.addPatient(new Patient("John Doe", 35, "Male", "123 Main St"));
        hospital.addPatient(new Patient("Jane Doe", 28, "Female", "456 Oak St"));

        hospital.addDoctor(new Doctor("Dr. Smith", "Cardiologist"));
        hospital.addDoctor(new Doctor("Dr. Johnson", "Orthopedic"));

        // Schedule sample appointments
        Patient patient = hospital.getPatients().get(0);
        Doctor doctor = hospital.getDoctors().get(0);
        hospital.scheduleAppointment(patient, doctor, "2024-02-23");

        // Display patient information
        System.out.println("Patients:");
        for (Patient p : hospital.getPatients()) {
            System.out.println("Name: " + p.getName() + ", Age: " + p.getAge() + ", Gender: " + p.getGender() + ", Address: " + p.getAddress());
        }

        // Display doctor information
        System.out.println("\nDoctors:");
        for (Doctor d : hospital.getDoctors()) {
            System.out.println("Name: " + d.getName() + ", Specialization: " + d.getSpecialization());
        }

        // Display appointment information
        System.out.println("\nAppointments:");
        for (Appointment a : hospital.getAppointments()) {
            System.out.println("Patient: " + a.getPatient().getName() + ", Doctor: " + a.getDoctor().getName() + ", Date: " + a.getDate());
        }
    }
}

