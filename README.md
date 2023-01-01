# HM Invent Coding Challenge

## Manually events task

### Overview

Given a set of events, each with a start time and end time, render the events on a
single day calendar (similar to Outlook, Calendar.app, and Google Calendar). There are
several properties of the layout:

No events may visually overlap.

- If two events collide in time, they MUST have the same width. This is an invariant. Call this width W
- W should be the maximum value possible without breaking the previous invariant.
- Each event is represented by a JavaScript object with a start and end attribute.
- The value of these attributes is the number of minutes since 9am. So {start:30, end:90} represents an event from 9:30am to 10:30am.
- The events should be rendered in a container that is 632px wide (600px + 16px padding on the left/right) and 720px long (the day will end at 9pm).
- The styling of the events should match the attached screenshot.

## Code Guidelines

Please use vue (preferred: vue3) with one page that consume events from attached
Backend mock server:

- GET http://localhost:3000/events
- RES [ {start: 30, end: 150}, {start: 540, end: 600}, {start: 560, end: 620}, {start: 610, end: 670} ]
  You can run Mocked server using:
- npm install
- npm run start

## Constraints:

- Only vue is allowed to structure the app and scss for styles.
- Using libraries that handle events is not allowed. Please provide a solution from scratch.
- Assume that 100 is the maximum number of events that can be rendered.
- Assume that data of events are valid. So no need to guard against invalid data.
- Solution needs to match the attached screenshot pixel perfectly.
- Solution should be submitted via git. Please create a private repo and share it with us.
- Please don’t share with your colleagues and friends as w

## Design:

![alt text](https://github.com/MuhammadMoftah]/events-task/blob/[branch]/events.jpeg?raw=true)
