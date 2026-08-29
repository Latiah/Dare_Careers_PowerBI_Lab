# Dare Careers — Learner's Dashboard (Power BI)

Tracks student progress across two training tracks — **Power BI Training** and **Cloud Training** — using attendance, participation, lab/quiz scores, and graduation/certification status.

## Data Model

Data Model

Six tables, built as a star schema with two shared dimensions (Learners and WeekDim/DateTable) connecting three fact tables:

Learners — Name, Email, Track, Cohort, Graduation Status, Certification Status, Program Status (dimension — one row per learner)
DateTable — Date, Week (dimension — one row per class date)
dim_week— Week, Month (dimension — one row per program week; sits upstream of DateTable and Assessments)
Attendance — daily Zoom records, Duration_Minutes, Attended/Absent (fact)
Assessments — weekly Lab & Quiz scores (fact)
Participation — daily participation records (fact)

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
