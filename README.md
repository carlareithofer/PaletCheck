# PaletCheck

**Find out in 30 seconds how much your team lifts by hand, and whether your bucket line can be palletized by a UR20 collaborative robot.**

🔗 **Live demo:** [carlareithofer.github.io/PaletCheck](https://carlareithofer.github.io/PaletCheck/)

<img width="400" height="240" alt="image" src="https://github.com/user-attachments/assets/15fc6dfb-5b4a-4624-abcd-bdf600b1caa3" />
<img width="400" height="240" alt="image" src="https://github.com/user-attachments/assets/f40a3af6-b6a8-4ae8-b28a-5b1566e57677" />


---

## About the project

PaletCheck was built for the **AI-Powered Business Challenge 2026**, organised by Start Your StartUP at POLITEHNICA Bucharest (20 November 2026). Teams of up to three received a real business case on the spot and had a few hours to build a complete business with AI. I took part solo.

**The case:** Tech-Con installed UR20 collaborative robots to palletize buckets at a food factory. How could similar robotic cells be promoted and sold to other factories in Romania?

**My answer:** a quick self-assessment tool for production managers at **paint and building-materials plants** (emulsion paints, fillers, adhesives), the first step before a technical evaluation.

## What it does

The user enters the data of one filling line:

- weight of a full bucket
- line rate (buckets per minute)
- shifts per day and operators palletizing per shift
- whether the bucket has a handle, whether the area is dusty, whether compressed air is available

and gets a report with:

- **tonnes lifted by hand every day** (and per operator, per shift, per year)
- estimated pallets per day and UR20 cells needed for the line rate
- a **compatibility verdict**: suitable, possibly suitable (to validate) or not suitable
- a checklist of what was verified and what still needs technical validation
- a **"Request a technical evaluation"** form (demo only, nothing is sent)

Three one-click examples show a suitable line, a bucket that is too heavy, and wrong or missing input.

## How the check works

| Check | Rule |
| --- | --- |
| Payload | bucket + gripper (~7 kg, assumption) must stay under the UR20's 25 kg payload |
| Rate | compared with the 6 buckets/min design target and the tested 7.4–8.6 buckets/min |
| Grip | a handle allows the tested pneumatic gripper; no handle means separate validation |
| Environment | the arm is IP65 rated; camera and gripper are checked for dust |
| Utilities | the gripper is pneumatic, so compressed air is required |

**Assumptions:** 7 productive hours per shift, 250 working days per year, gripper weight ~7 kg. Reference values come from a single test application and are not guarantees.

## Features

- Bilingual interface (Romanian / English), the choice is remembered
- Scroll animation: a hand-drawn SVG robot arm lifts a bucket-shaped form on a cable
- Report styled as a spiral notebook page
- Separate pages for the UR20 specs and "About"
- Responsive layout for phone and desktop
- Respects the reduced-motion accessibility setting

## Tech

- A single self-contained `index.html`: HTML, CSS and vanilla JavaScript, no frameworks or build step
- Hand-built SVG illustrations and kinematic arm animation
- Images embedded in the file
- Hosted on GitHub Pages

## Project structure

```
PaletCheck/
├── index.html      the whole web app
├── README.md
└── docs/           (optional) strategy, financial model, poster, pitch, AI log
```

## How it was built

The app was built with **Claude (Anthropic)** as an AI partner during the challenge. My part: choosing the market segment and the product idea, designing the layout (sketched on paper), the creative ideas (the robot pulling the page, the bucket-shaped form, the notebook report), photographing the robot at the event and verifying the AI's output.

Two corrections I made by checking the AI's work:

- The first version assumed a **20 kg** payload. I photographed the robot's nameplate at the event, which says **25 kg**, and corrected the app.
- A quick financial estimate gave **17** robotic cells to reach the profit target. Including tax and other costs, the correct answer was **22**.

## Other deliverables

Built in the same 3.5 hours: a one-page strategy, a financial model with formulas, a poster, a 5-slide pitch and an AI log.

## Disclaimer

PaletCheck is a **contest prototype**. It is not an official website of Tech-Con, Universal Robots or any other company, and all data entered is fictional. Images of the UR20 arm are presentation materials from Universal Robots; the photos of the demo cell were taken by me at the event.

## Author

**Carla Reithofer** · Electronics student, Faculty of Engineering in Foreign Languages (FILS), POLITEHNICA Bucharest
