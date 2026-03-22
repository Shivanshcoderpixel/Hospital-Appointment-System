## Modules of Hospital Appointment System

### 1. Doctor Management Module

**Purpose:** Manage doctor details and availability

**Functions:**

* Add new doctors
* Store doctor information such as ID, name, and specialization
* Track whether a doctor is available or busy

**Code Mapping:**

* `Doctor` class
* `addDoctor()` method in `HospitalSystem`

---

### 2. Patient Management Module

**Purpose:** Handle patient registration and maintain patient data

**Functions:**

* Register new patients
* Store patient details such as ID, name, and age

**Code Mapping:**

* `Patient` class
* `addPatient()` method in `HospitalSystem`

---

### 3. Appointment Booking Module

**Purpose:** Book appointments between patients and doctors

**Functions:**

* Display available doctors
* Select a doctor and a patient
* Generate a unique token number
* Create and assign an appointment

**Code Mapping:**

* `Appointment` class
* `bookAppointment()` method in `HospitalSystem`

---

### 4. Token / Queue Management Module

**Purpose:** Manage patient flow using a First-Come First-Serve (FIFO) approach

**Functions:**

* Maintain a queue of appointments
* Ensure patients are served in order of arrival
* Assign token numbers to each appointment

**Code Mapping:**

* `Queue<Appointment>` implemented using `LinkedList`
* `tokenCounter` variable

---

### 5. Patient Serving Module

**Purpose:** Handle the process of serving patients

**Functions:**

* Remove the next patient from the queue
* Mark the doctor as available again
* Display details of the patient being served

**Code Mapping:**

* `servePatient()` method in `HospitalSystem`

---

### 6. Appointment Viewing Module

**Purpose:** Display all pending appointments

**Functions:**

* Show all appointments currently in the queue
* Display token number, patient name, and assigned doctor

**Code Mapping:**

* `viewAppointments()` method in `HospitalSystem`

---

### 7. User Interface Module (Console)

**Purpose:** Provide interaction between the user and the system

**Functions:**

* Display menu options
* Accept user input
* Navigate between different system functionalities

**Code Mapping:**

* `main()` method in `HospitalSystem`
