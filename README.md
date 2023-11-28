# Office Work Tracker

## Summary

This project contains a spreadsheet I created to meet personal interest/needs. 
Colleagues have found it useful, so I share a blanked/empty copy here.

I am certainly open to suggestions/request for tweaks and adjustments -- as one of those weird people who likes techy/interesting problems (even in personal time!), I'm always up for a chat about how something might be done.

That said, please do not be offended if I decline to merge it in and/or suggest it be kept within a fork of this project :) 


## Overview

### Sheet: `SUMMARY`

This sheet should not normally be edited.

![image](https://github.com/RogerHowellDfE/Office-Work-Tracker/assets/96429508/c6b03e07-41f2-4faf-8990-fad1853841bf)


- This sheet contains an overview summary of the data contained within the data sheets.
  - Specifically, each month is represented by a row with data about that month in columns.
  - Very basic totals are displayed for the number of days in each "work location" categories.
  - This includes a breakdown of "home" working days vs "office" working days (incl. "outside of office"/"site visit").
  - There is also a column to indicate the minimum number of "office days" required to meet a 40% and 60% threshold for that given month
    (accounting for non-working days such as weekends, annual-leave, bank-holidays, personal non-working-days, etc.)
- The "Month" value is used within the aggregation formulae to fetch data from the relevant tabs/sheets.
  - My need is to aggregate by month therefore each sheet represents an individual month.
  - Your needs might be weekly, quarterly, yearly, or something else - in which case you can rename the sheets and update the content accordingly to meet your needs.


### Sheet: `OCTOBER-2023` / `NOVEMBER-2023` / etc.

Only the blue "work location category" column should normally be edited.
All other cells are calculated based on the values in this column.

![image](https://github.com/RogerHowellDfE/Office-Work-Tracker/assets/96429508/6d1a6b64-85fc-496c-98e0-7c440eac940e)


- These sheets allow you to enter your working location for each day.
- Data validation rules present you a drop-down list of available options for that date.
  - These are populated from the values within the `SUMMARY` tab.
  - Validation rules are configured to provide a warning if an uncrecognised value is entered - specifically, the monthly aggregations and percentage of office-day calculations may be incorrect.
- A variety of conditional formatting rules provide affordances/indications about values.
  - For example:
    - weekend dates are shaded with a light gray background,
    - where a work location category is unspecified and there is a date then it is shaded light blue,
    - the `% OFFICE WORKING` column is highlighted on a gradient where 40% office attendance is yellow, while less than this graduates towards red and above this graduates toward green.
- Columns D:K
  - Personally I find these columns useful (able to highlight values and see the sum in the taskbar for example, and generally I like to see granular data/intermediary steps to be able to follow the logic).
  - If you do not find them useful, or if a column is never applicable to you (e.g., site visits or a regular non-working day), you may wish to hide these columns (highlight the column(s) and select "Hide").
- `RUNNING TOTAL - OFFICE`
  - This column heading is dynamic, and will indicate the number of days required to meet a 40% / 60% threshold.
  - Where these thresholds are a decimal (e.g. 7.6 days), given that recording/reporting of this data is at the "day" granularity, this indicates you will need to record attendance for eight days that month to exceed this threshold.
  - This takes into account/adjusts for non-working days such as weekends and annual leave.
- `% OFFICE WORKING`
  - The values in this column are dynamic show you both your running total to that date of the month, and what your end-of-month percentage will be.
  - This presumes that blank dates are not "office" days


**Example partially-completed monthly sheet**

![image](https://github.com/RogerHowellDfE/Office-Work-Tracker/assets/96429508/134b4bfc-a0b5-4b85-8ddf-ce78f0f52900)

- Note that the start of the month stays at a 0% total given that, to that point, all recorded dates how as either bank-holiday/weekend/home-working dates.
- When "office" days begin to be recorded, this brings the running total/percentage up.
- Where there is then, later in the month, a mix of home working dates and missing data (empty, lightly blue shaded cells), the running total begins to drop.
  - This feature can be used to plan your office days into the remainder of the month to meet your 40%/60% thresholds.
