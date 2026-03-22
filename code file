import java.util.*;

// Doctor class
class Doctor {
    int id;
    String name;
    String specialization;
    boolean available;

    Doctor(int id, String name, String specialization) {
        this.id = id;
        this.name = name;
        this.specialization = specialization;
        this.available = true;
    }

    @Override
    public String toString() {
        return id + " - Dr. " + name + " (" + specialization + ") - " +
               (available ? "Available" : "Busy");
    }
}

// Patient class
class Patient {
    int id;
    String name;
    int age;

    Patient(int id, String name, int age) {
        this.id = id;
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return id + " - " + name + " (Age: " + age + ")";
    }
}

// Appointment class
class Appointment {
    int tokenNumber;
    Doctor doctor;
    Patient patient;

    Appointment(int tokenNumber, Doctor doctor, Patient patient) {
        this.tokenNumber = tokenNumber;
        this.doctor = doctor;
        this.patient = patient;
    }

    @Override
    public String toString() {
        return "Token: " + tokenNumber + ", Patient: " + patient.name +
               ", Doctor: Dr. " + doctor.name;
    }
}

// Main hospital system
public class HospitalSystem {

    static ArrayList<Doctor> doctors = new ArrayList<>();
    static ArrayList<Patient> patients = new ArrayList<>();
    static Queue<Appointment> appointmentQueue = new LinkedList<>();

    static int tokenCounter = 1;

    // Add a doctor
    static void addDoctor(Scanner sc) {
        System.out.print("Enter Doctor ID: ");
        int id = sc.nextInt();
        sc.nextLine();

        System.out.print("Enter Name: ");
        String name = sc.nextLine();

        System.out.print("Enter Specialization: ");
        String spec = sc.nextLine();

        doctors.add(new Doctor(id, name, spec));
        System.out.println("Doctor added successfully!");
    }

    // Register a patient
    static void addPatient(Scanner sc) {
        System.out.print("Enter Patient ID: ");
        int id = sc.nextInt();
        sc.nextLine();

        System.out.print("Enter Name: ");
        String name = sc.nextLine();

        System.out.print("Enter Age: ");
        int age = sc.nextInt();

        patients.add(new Patient(id, name, age));
        System.out.println("Patient registered successfully!");
    }

    // Book an appointment
    static void bookAppointment(Scanner sc) {
        if (doctors.isEmpty() || patients.isEmpty()) {
            System.out.println("Please add doctors and patients first!");
            return;
        }

        System.out.println("Available Doctors:");
        for (Doctor d : doctors) {
            if (d.available) {
                System.out.println(d);
            }
        }

        System.out.print("Enter Doctor ID: ");
        int docId = sc.nextInt();
        sc.nextLine();

        Doctor selectedDoctor = null;
        for (Doctor d : doctors) {
            if (d.id == docId && d.available) {
                selectedDoctor = d;
                break;
            }
        }

        if (selectedDoctor == null) {
            System.out.println("Doctor not available or not found.");
            return;
        }

        System.out.println("Patient List:");
        for (Patient p : patients) {
            System.out.println(p);
        }

        System.out.print("Enter Patient ID: ");
        int patId = sc.nextInt();

        Patient selectedPatient = null;
        for (Patient p : patients) {
            if (p.id == patId) {
                selectedPatient = p;
                break;
            }
        }

        if (selectedPatient == null) {
            System.out.println("Patient not found.");
            return;
        }

        Appointment appt = new Appointment(tokenCounter++, selectedDoctor, selectedPatient);
        appointmentQueue.add(appt);
        selectedDoctor.available = false;

        System.out.println("Appointment booked! Token number: " + appt.tokenNumber);
    }

    // Serve the next patient
    static void servePatient() {
        if (appointmentQueue.isEmpty()) {
            System.out.println("No appointments in the queue.");
            return;
        }

        Appointment appt = appointmentQueue.poll();
        appt.doctor.available = true;

        System.out.println("Serving: " + appt);
    }

    // View all pending appointments
    static void viewAppointments() {
        if (appointmentQueue.isEmpty()) {
            System.out.println("No appointments scheduled.");
            return;
        }

        System.out.println("Pending Appointments:");
        for (Appointment a : appointmentQueue) {
            System.out.println(a);
        }
    }

    // Main menu
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        while (true) {
            System.out.println("\n--- Hospital Appointment System ---");
            System.out.println("1. Add Doctor");
            System.out.println("2. Add Patient");
            System.out.println("3. Book Appointment");
            System.out.println("4. Serve Patient");
            System.out.println("5. View Appointments");
            System.out.println("6. Exit");

            System.out.print("Enter choice: ");
            int choice = sc.nextInt();

            switch (choice) {
                case 1:
                    addDoctor(sc);
                    break;
                case 2:
                    addPatient(sc);
                    break;
                case 3:
                    bookAppointment(sc);
                    break;
                case 4:
                    servePatient();
                    break;
                case 5:
                    viewAppointments();
                    break;
                case 6:
                    System.out.println("Exiting the system. Goodbye!");
                    sc.close();
                    return;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        }
    }
}
