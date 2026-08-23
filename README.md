# Dare Careers — Learner's Dashboard (Power BI)

Tracks student progress across two training tracks — **Power BI Training** and **Cloud Training** — using attendance, participation, lab/quiz scores, and graduation/certification status.

## Data Model

Four tables, connected through a central **Learners** table (by Email):

- **Learners** — Name, Email, Track, Cohort, Graduation Status, Certification Status, Program Status
- **Attendance** — daily Zoom records, Duration_Minutes, Attended/Absent
- **Assessments** — weekly Lab & Quiz scores
- **Participation** — daily participation records

**Attendance rule**: marked "Attended" only if session duration > 30 minutes.

## Pages

**Page 1 — Overall Performance**

Cards: Total Learners, Graduations, Certifications, Dropouts

Charts: Graduation/Certification/Dropout Rate, Avg Attendance, Avg Participation, Avg Assessment Score — all by Track

Slicers: Track, Cohort, Graduation Status, Certification Status, Assessment Type

**Page 2 — Detailed Learner Insights**

Table: per-learner Attendance, Participation, Assessment Score

Cards: Count of Labs, Avg Labs Completed, Total Hours in Class, per-learner averages

Slicers: Week, Month, Track, Certification Status, Cohort, Program Status

## How We Implemented Key Fields

- **Dropout Rate** was calculated as everyone with Graduation Status = "Non Graduate."

- **Program Status** was derived as: Graduate → "Completed", Non Graduate → "Ongoing".

- **Cohort** was set to "Cohort 1" for all learners; charts are grouped by Track.
