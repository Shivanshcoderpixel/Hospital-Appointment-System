# Hospital-Appointment-System
The Hospital Appointment System is a console-based Java application designed to reduce waiting times in hospitals by efficiently managing patient appointments.  This system allows patients to book appointments with doctors, checks doctor availability, and manages a token-based queue system for smooth patient flow.
Here’s a **more human‑sounding, natural, and slightly shorter** version of your project description:

### Why I Built This(problrm statment)

I’ve often waited a long time at hospitals, not knowing when my turn would come or whether the doctor I wanted was even available.  
I wanted to build a basic system that:

- Lets patients **book an appointment**  
- Shows **which doctors are free**  
- Uses a **token system** (like in real clinics)

### What This Project Can Do
- Add doctors with their specialization  
- Register patients  
- Book appointments with available doctors  
- Issue a unique **token number**  
- Serve patients in the order they arrived (**FIFO**)  
- View all **pending appointments**

### What I Learned
While building this, I got hands‑on practice with:
- **OOP concepts** like classes, objects, encapsulation, and modularity  
- **Data structures** such as:  
  - `ArrayList` for storing doctors and patients  
  - `Queue` (using `LinkedList`) to manage tokens  
  - `HashMap` for quick appointment lookups  

It helped me connect theory to something I could actually see working.

### Tech Stack
- Java  
- Java Collections Framework  
- Console‑based UI  

### How to Run This Project
1. Clone the repo  
   ```bash
   git clone https://github.com/your-username/hospital-appointment-system.git
   ```
2. Go to the project folder  
   ```bash
   cd hospital-appointment-system
   ```
3. Compile the code  
   ```bash
   javac HospitalSystem.java
   ```
4. Run the program  
   ```bash
   java HospitalSystem
   ```
### How It Works (Simple Flow)
1. Add a doctor  
2. Register a patient  
3. Book an appointment  
4. Get a token number  
5. Serve patients in the order they arrived
   
### Future Improvements
I’d like to extend this system by adding:
- A GUI (Java Swing / JavaFX)  
- A database (MySQL)  
- A login system (Admin / Patient)  
- Time‑slot based booking  
- Emergency priority handling

### Author
Shivansh Jaswal
