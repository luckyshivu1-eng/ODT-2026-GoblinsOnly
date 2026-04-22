Open Design and Technology
Final Project README

Project Weight: 70%
Team Size: 2 students
Project Duration: 4 weeks
Class Time Available: 6 hours per class
Total Time Available: 48 effort-hours per team
Project Type: Playful, interactive, technology-based experience

1. Team Identity
1.1 Studio / Group Name

Goblins Only

1.2 Team Members
| Name    | Primary Role           | Secondary Role | Strengths Brought to the Project           |
| ------- | ---------------------- | -------------- | ------------------------------------------ |
| Smera   | Fabrication and Design | Electronics    | Form development, prototyping, assembly    |
| Shivani | Electronics and Coding | Mechanics      | Circuit building, debugging, ESP32 control |

1.3 Project Title

Dart Goblin Inspired Gel Blaster

1.4 One-Line Pitch

A mobile Dart Goblin inspired gel launcher that can be manually driven through an app and fires gel projectiles through a flute.

1.5 Expanded Project Idea

The project is a mobile robotic system inspired by the Dart Goblin from Clash Royale. It consists of a wheeled base and a gel-shooting mechanism integrated into a flute-like structure to resemble the character. The robot is controlled through a mobile application, allowing the user to drive it and aim by repositioning the entire robot before shooting.

The experience is designed to be playful and interactive. Movement combined with shooting creates a satisfying interaction. The character-inspired design makes the system more engaging compared to a purely technical robot. The project integrates multiple technologies, including ESP32 Wi-Fi communication, a motor driver for movement, a relay module for triggering the gel blaster, and a mobile app built using MIT App Inventor.

2. Philosophy Fit
2.1 Experience, Not Social Problem
2.2 What kind of experience are you creating?

The experience is a remote-controlled robotic system where the user drives a robot and shoots gel projectiles.

The user should feel in control, curious, and engaged.

The interaction encourages repeated use because positioning and movement create different outcomes each time.

2.3 Design Persona

We are designing this project as if we are a small creative studio making a playable object for teens and classmates.

3. Inspiration
3.1 References
   
| Source Type | Title / Link               | What Inspired You                          |
| ----------- | -------------------------- | ------------------------------------------ |
| Video Game  | Clash Royale (Dart Goblin) | Character design and shooting concept      |
| Toy         | Nerf Blasters              | Shooting interaction and feedback          |
| YouTube     | ESP32 Robot Projects       | Integration of motors and wireless control |

3.2 Original Twist

The project transforms a digital game mechanic into a physical, character-driven interactive object. The shooting direction is controlled entirely by how the robot is positioned, making movement and navigation central to the interaction. The core behavior of the original game character is preserved while adapting it to real-world constraints like movement and space.

4. Project Intent
4.1 Core Interaction Loop

Drive the robot, position it, shoot, reposition, and repeat.

4.2 Intended Player / Audience

| Question                            | Response                         |
| ----------------------------------- | -------------------------------- |
| Who is this for?                    | Teens and classmates             |
| Age range                           | 14 to 25                         |
| Solo or multiplayer                 | Solo                             |
| Expected duration of one round      | Depends on available ammunition  |
| What should the player feel?        | In control, curious, and engaged |
| Is explanation required before use? | Minimal                          |

4.3 Player Journey

Approach: The player sees a wheeled robot with a flute-shaped launcher.

Start: The player opens the application and connects to the robot’s Wi-Fi network.

First Action: The player tests movement controls.

Main Interaction: The player drives the robot and shoots at targets.

System Response: The robot moves and fires based on input commands.

Win / Lose / End Condition: The interaction ends when the user stops or ammunition runs out.

Reset: The player reloads and continues.

4.4 Rules of Play
Movement is controlled through the application
Shooting is controlled through the application
Aiming is done by repositioning the robot
The round ends when the user stops or ammunition runs out
5. Definition of Success
5.1 Definition of “Playable”
The robot powers on correctly
Movement responds accurately to input
Shooting functions reliably
Communication between the application and the robot is stable
5.2 Minimum Viable Version

A basic system with movement and shooting controlled through the application.

5.3 Stretch Features

Improved structural design and finishing of the character.

6. System Overview
   
6.1 Project Type

Electronics-based
Mechanical
App-connected
Motorized
Fabricated structure
Game logic based
Installation / tabletop experience

6.2 High-Level System Description

The system uses an ESP32 as the central controller, which creates a Wi-Fi access point. The mobile application sends HTTP requests containing action commands. The ESP32 processes these commands and controls the motor driver for movement and a relay module for activating the gel blaster. Movement is achieved using differential drive, and shooting is triggered electronically. All components are mounted on a chassis, and direction is controlled by repositioning the robot.

6.3 Input / Output Map

| System Part                  | Type            | What It Does                            |
| ---------------------------- | --------------- | --------------------------------------- |
| Mobile application           | Input           | Sends movement and shooting commands    |
| ESP32                        | Processing      | Processes commands and controls outputs |
| Motor driver and motors      | Output          | Moves the robot                         |
| Relay module and gel blaster | Output          | Fires projectiles                       |
| Chassis                      | Physical Action | Supports structure and movement         |

7. Sketches and Visual Planning
7.1 Concept Sketch

7.2 Labeled Build Sketch

7.3 Approximate Dimensions

| Dimension        | Value                |
| ---------------- | -------------------- |
| Length           | 19 cm                |
| Width            | 16 cm                |
| Height           | 43 cm                |
| Estimated weight | More than 1 kilogram |

Estimated weight	More than 1 kilogram
8. Mechanical Planning
8.1 Mechanical Features
Wheels
8.2 Mechanical Description

The robot uses a four-wheel chassis. Motors are grouped into left and right sides to allow differential drive movement.

8.3 Motion Planning

The robot moves forward, backward, and turns left or right using differential drive controlled by the motor driver. Movement continues only while commands are being received from the application. If no command is received within a short duration, the system automatically stops the motors using a timeout mechanism. This prevents unintended continuous movement. Possible issues include slipping, uneven turning, and reduced control precision.

8.4 Simulation / CAD / Animation Before Making

Not applicable, as no digital simulation was used.

8.5 Changes After Digital Testing

Not applicable.

9. Electronics Planning
9.1 Electronics Used
   
| Component            | Quantity | Purpose                   |
| -------------------- | -------- | ------------------------- |
| ESP32                | 1        | Main controller           |
| DC motors            | 4        | Movement                  |
| Motor driver (L298N) | 1        | Controls motors           |
| Relay module         | 1        | Controls firing mechanism |
| Gel blaster          | 1        | Shooting mechanism        |

9.2 Wiring Plan

The battery powers the motor driver. A buck converter steps down voltage to power the ESP32 through the 3.3V pin. The ESP32 connects to the motor driver using GPIO pins 22, 23, 21, and 18. The relay module is connected to GPIO 2. Motors are grouped into left and right sides. All components share a common ground.

9.3 Circuit Diagram

9.4 Power Plan

| Question         | Response                                                |
| ---------------- | ------------------------------------------------------- |
| Power source     | Battery (two 18650 cells)                               |
| Voltage required | Approximately 7.4 volts                                 |
| Current concerns | High current draw from motors and gel blaster           |
| Safety concerns  | Avoid overheating, short circuits, and incorrect wiring |

10. Software Planning
    
10.1 Software Tools
    
| Tool             | Purpose                           |
| ---------------- | --------------------------------- |
| MicroPython      | Programming the ESP32             |
| MIT App Inventor | Developing the mobile application |

10.2 Software Logic

On startup, the ESP32 initializes all pins and creates a Wi-Fi access point. The system listens for HTTP requests from the mobile application. Each request contains an action parameter such as forward, backward, left, right, stop, or shoot. Based on this action, the ESP32 controls the motor driver or activates the relay module. A timeout mechanism continuously checks if commands are being received. If no command is received within the defined time, the motors are stopped automatically for safety.

10.3 Code Flowchart

Put image here

10.4 Pseudocode

Start system
Initialize Wi-Fi access point
Set motor pins as outputs
Set relay to off
Stop motors

Loop:
Receive request
If action is forward, move forward
If action is backward, move backward
If action is left, turn left
If action is right, turn right
If action is stop, stop motors
If action is shoot, activate relay, wait, deactivate relay, stop motors
If no command is received within timeout, stop motors

Repeat loop

11. MIT App Inventor Plan
11.1 Is an app part of this project?

Yes

11.2 Why is the app needed?

The application allows remote control of the robot’s movement and shooting.

11.3 App Features

| Feature             | Purpose                     |
| ------------------- | --------------------------- |
| Directional buttons | Control movement            |
| Shoot button        | Activate shooting mechanism |

11.4 UI Mockup

11.5 App Screen Flow

Step 1: Open application
Step 2: Connect to robot’s Wi-Fi
Step 3: Control movement and shooting
Step 4: Exit

12. Bill of Materials
12.1 Full BOM

| Item                 | Quantity         | In Kit? | Need to Buy? | Estimated Cost |
| -------------------- | ---------------- | ------- | ------------ | -------------- |
| ESP32                | 1                | No      | Yes          | 400            |
| Motor driver (L298N) | 1                | No      | Yes          | 179            |
| Relay module         | 1                | No      | Yes          | 65             |
| Buck converter       | 1                | No      | Yes          | 65             |
| Gel blaster          | 1                | No      | Yes          | 900            |
| Chassis              | 1                | No      | Yes          | 197            |
| Motors and wheels    | 1 set            | No      | Yes          | 389            |
| Jumper wires         | Approximately 20 | Yes     | No           | 100            |
| Battery and holder   | 1 set            | No      | Yes          | 251            |
| Power module         | 1                | No      | Yes          | 65             |

12.2 Material Justification

All components were selected based on availability, compatibility with the ESP32, and ease of integration.

12.3 Items to Purchase Separately

| Item                  | Why Needed                | Purchase Link  | Latest Safe Date to Procure | Status   |
| --------------------- | ------------------------- | -------------- | --------------------------- | -------- |
| All listed components | Required for system build | Not applicable | Week 1                      | Received |

12.4 Budget Summary

| Budget Item           | Estimated Cost     |
| --------------------- | ------------------ |
| Electronics           | 1674               |
| Mechanical parts      | 586                |
| Fabrication materials | 0                  |
| Purchased extras      | 316                |
| Contingency           | 200                |
| Total                 | Approximately 2776 |

12.5 Budget Reflection

Costs were managed by selecting readily available components and avoiding unnecessary additions.

13. Planning the Work
13.1 Team Working Agreement

Work was divided based on strengths, but both members contributed across all areas when needed. Shivani focused more on electronics, coding, and app development, while Smera focused more on fabrication and mechanical assembly. However, both members were involved in testing, debugging, and integration. Decisions were made jointly after testing different approaches. Progress was reviewed at the end of each session, and if a task was delayed, both members worked together to resolve it. Documentation was updated regularly throughout the process.

13.2 Task Breakdown

| Task ID | Task                                | Owner   | Estimated Hours | Deadline | Dependency     | Status |
| ------- | ----------------------------------- | ------- | --------------- | -------- | -------------- | ------ |
| T1      | Finalize concept                    | Both    | 2               | Week 1   | None           | Done   |
| T2      | Complete BOM                        | Both    | 1               | Week 1   | T1             | Done   |
| T3      | Test ESP32 and motors               | Shivani | 3               | Week 1   | T1             | Done   |
| T4      | Assemble chassis                    | Smera   | 4               | Week 2   | T1             | Done   |
| T5      | Integrate motor driver              | Both    | 3               | Week 2   | T3             | Done   |
| T6      | Add gel blaster control using relay | Shivani | 3               | Week 2   | T3             | Done   |
| T7      | Build app (MIT App Inventor)        | Shivani | 4               | Week 2   | T3             | Done   |
| T8      | Integrate full system               | Both    | 5               | Week 3   | T4, T5, T6, T7 | Done   |
| T9      | Debug and fix issues                | Both    | 3               | Week 3   | T8             | Done   |
| T10     | Playtesting                         | Both    | 2               | Week 4   | T8             | Done   |
| T11     | Final documentation                 | Both    | 4               | Week 4   | T10            | Done   |

13.3 Responsibility Split

Area | Main Owner | Support Owner
Concept and gameplay | Both | —
Electronics | Shivani | Smera
Coding | Shivani | Smera
App | Smera | Shivani
Mechanical build | Smera | Shivani
Testing | Both | —
Documentation | Both | —

14. Weekly Milestones
14.1 Four-Week Plan

Week 1 — Plan and De-risk

Idea finalized
Core interaction decided
BOM completed
Basic testing completed

Week 2 — Build Subsystems

Electronics tested
Movement working
App control working

Week 3 — Integrate

Full system assembled
Movement and shooting integrated

Week 4 — Refine and Finish

Issues fixed
Testing completed
Final documentation completed
14.2 Weekly Update Log

| Week   | Planned Goal         | What Actually Happened   | What Changed              | Next Steps      |
| ------ | -------------------- | ------------------------ | ------------------------- | --------------- |
| Week 1 | Planning and testing | Basic system tested      | Switched to Wi-Fi control | Build structure |
| Week 2 | Build subsystems     | Movement and app working | Adjusted wiring           | Add shooting    |
| Week 3 | Integration          | Full system working      | Simplified wiring         | Testing         |
| Week 4 | Finalization         | Stable system            | Minor fixes               | Submission      |

15. Risks and Unknowns
15.1 Risk Register
    
| Risk                             | Type      | Likelihood | Impact | Mitigation Plan            | Owner |
| -------------------------------- | --------- | ---------- | ------ | -------------------------- | ----- |
| Relay always on                  | Technical | Medium     | High   | Correct wiring and logic   | Both  |
| Jumper cap issue on motor driver | Technical | Medium     | Medium | Verify connections         | Both  |
| Battery not charged              | Technical | High       | High   | Ensure charging before use | Both  |

15.2 Biggest Unknown Right Now

Power stability when running motors and gel blaster simultaneously.

16. Testing and Playtesting
16.1 Technical Testing Plan
    
| What Needs Testing | How You Will Test It     | Success Condition |
| ------------------ | ------------------------ | ----------------- |
| Wi-Fi connection   | Reconnect multiple times | Stable connection |
| Movement           | Drive in all directions  | Accurate response |
| Shooting           | Trigger repeatedly       | Consistent firing |

16.2 Playtesting Plan

| Question                             | How You Will Check |
| ------------------------------------ | ------------------ |
| Do players understand what to do?    | Observe usage      |
| Is the interaction satisfying?       | Collect feedback   |
| Do players want another turn?        | Repeat interaction |
| Is the response clear and immediate? | Observe delay      |

16.3 Testing and Debugging Log

| Date  | Problem Found                       | Type      | What You Tried         | Result | Next Action      |
| ----- | ----------------------------------- | --------- | ---------------------- | ------ | ---------------- |
| Day 1 | Relay always on                     | Technical | Fixed logic and wiring | Worked | Continue testing |
| Day 2 | Motor not working due to ENB jumper | Technical | Corrected jumper       | Worked | Continue         |
| Day 3 | Battery not charged                 | Technical | Charged battery        | Worked | Ensure charging  |

16.4 Playtesting Notes

| Tester    | What They Did          | What Confused Them | What They Enjoyed    | What You Will Change |
| --------- | ---------------------- | ------------------ | -------------------- | -------------------- |
| Classmate | Used controls and shot | Initial controls   | Shooting interaction | Improve clarity      |

17. Build Documentation
17.1 Fabrication Process

The chassis was assembled using a kit. Motors were mounted and connected to the motor driver. The ESP32, relay, and wiring were secured. The gel blaster was mounted and aligned.

17.2 Build Photos

17.3 Version History

| Version | Date   | What Changed         | Why                     |
| ------- | ------ | -------------------- | ----------------------- |
| v1      | Week 1 | Basic movement       | Initial testing         |
| v2      | Week 2 | App control          | Required remote control |
| v3      | Week 3 | Shooting integration | Full functionality      |

18. Final Outcome
18.1 Final Description

A mobile robot controlled through a mobile application that can move and shoot gel projectiles.

18.2 What Works Well
Movement is responsive
Shooting is consistent
Application control is functional
18.3 What Still Needs Improvement
Power stability
Wiring organization
Control precision
18.4 What Changed From the Original Plan

The project evolved into a fully integrated mobile system with wireless control and shooting functionality.

19. Reflection
19.1 Team Reflection

The team worked effectively by dividing tasks based on strengths.

19.2 Technical Reflection

The project provided experience in integrating electronics, programming, and mechanical systems.

19.3 Design Reflection

The importance of usability and clear interaction design was understood.

19.4 If You Had One More Week

We would improve power stability and clean up the structure to hide wiring and improve finishing.

20. Final Submission Checklist
All sections are filled
Image placeholders are added
Testing is documented
Reflection is complete

22. Suggested Repository Structure

project-repo/
├── README.md
├── images/
├── code/
├── cad/
└── docs/

22. Instructor Review
22.1 Proposal Approval
22.2 Midpoint Review
22.3 Final Review Notes
