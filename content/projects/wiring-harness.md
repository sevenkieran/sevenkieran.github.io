---
title: "FSAE Wiring Harness"
date: 2024-12-10
summary: "Established a new process for designing and manufacturing a wiring harness."
featured_image: "/images/Automotive-Wiring-Harness.jpg" 
---

## The Challenge

In many vehicles, the wiring harness is the critical nervous system connecting software/electrical controls to mechanical systems. The past two NovaRacing cars suffered from serious electrical unreliabilities. In 2023, team had even failed the most important event due to an electrical unreliability. Valuable track time was frequently lost to troubleshooting loose connections and shorts, resulting in only 200 miles of total testing distance last year.

When I became Electrical Lead, I realized the team couldn't create any advanced or cool projects if the car couldn't run reliably. To solve this problem, I established a new design process focused around organization, delibrate design, and documentation.

## The Design Process

### 1. Component Definition 
This process begins with creating a master Components List. It contains every electrical component with the correct pinouts, connectors, and wire gauge. It also defines what each component will connect to, which will help with future planning.

### 2. Pinout Documentation
From the Components List, the pinouts for the major devices can be created. Here we make the pinouts for any device with complex I/O including the ECU (electronic control unit), PDM (power distribution module), dashboard, and others as needed.

### 3. Wire Layout
The wire bundle layout is designed in RapidHarness. RapidHarness is a great tool for generating documentation and bill of materials. The wires are grouped into branch points and bundles that correspond to the chassis tubes and nodes. Wire routing is designed to simplify harness manufacturing by minimizing the number of bundles and branch points with the secondary goal is to minimize wire lengths for weight reduction. Splices are used to eliminate redundant wires in the power and ground busses.

### 4. Cutlist and Concentric Twist Planning
The wire cutlist is exported from RapidHarness into excel. Here, wire idents are applied with the resistor color code as a simple, lightweight solution to ensuring each wire can be differentiated in function easily. The concentric twist layers are also planned here based off where the wires will branch out.

### 5. Bill of Materials
Materials are delibrately selected to ensure reliability. The harness should be able to handle intense vibrations, high heat from the exhaust, abrasion, rain, dirt, and the *occasional* oil leak. With so many little parts, a BoM is incredibly valuable in staying organized and maintaining timelines.

### 6. Manufacturing
Now the fun begins! I won't go too in detailed in this process, as it feels more like an art than engineering. Here are some of the things I have learned from manufacturing:
- **Have high standards**: Many hands will help create the design, and some are more experienced and detailed oriented than others.
- **Test before installing**: Here's where younger members become super useful. Using a multimeter, connectivity test the entire harness to ensure everything matches the design.
- **Prevent mistakes now**: During manufacturing, it is still easy to service.