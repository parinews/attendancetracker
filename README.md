# Attendance Tracker

A modern, mobile-first web application for tracking employee attendance with a clean, cool-toned interface. Built with vanilla HTML, CSS, and JavaScript, this app stores all data locally in the browser.

## Features

- **Yearly Summary View**: Overview of all employees' days off for the current year
- **Monthly Summary View**: Detailed monthly attendance tracking with navigation
- **Employee Management**: View individual employee calendars and attendance details
- **Color-Coded Indicators**: 
  - **Employee Off** (Light Purple-Blue): Days taken by employees
  - **Employer Given Off** (Teal-Blue): Days given by employer
- **Interactive Calendar**: Click on dates to mark attendance status
- **Data Persistence**: All data stored locally in browser (localStorage)
- **Reset Functionality**: Clear all data option at the bottom
- **Mobile-First Design**: Optimized for mobile and desktop devices

## Technology Stack

- **Frontend**: Pure HTML5, CSS3, and Vanilla JavaScript
- **Storage**: Browser localStorage (no backend required)
- **No Dependencies**: Zero external libraries or frameworks

## Getting Started

### Installation

1. **Download or clone** the repository
2. **Open `attendance.html`** in a web browser
   - Simply double-click the file, or
   - Use a local server (recommended):
     ```bash
     # Python
     python3 -m http.server 8000
     
     # Node.js
     npx serve
     ```
3. **Access the app** at `http://localhost:8000/attendance.html`

### First Use

The app comes pre-loaded with three default employees:
- Sarita
- Puja
- Jayshree

You can start tracking attendance immediately or clear the data to start fresh.

## Usage Guide

### Viewing Summaries

1. **Yearly Summary** (Top Section):
   - Shows total days off for all employees in the current year
   - Displays Employee and Employer counts per employee
   - Automatically updates as you mark attendance

2. **Monthly Summary** (Bottom Section):
   - Shows attendance for the selected month
   - Use ← Prev and Next → buttons to navigate months
   - Click on any employee card to view their detailed calendar

### Marking Attendance

1. **Click on an employee card** from the monthly summary
2. **View the calendar** showing all days of the month
3. **Click on any date** to open the attendance selector
4. **Choose an option**:
   - **Employee Off**: Counts toward monthly allowance (2 days/month)
   - **Employer Given Off**: Does not count toward allowance
   - **Remove**: Clear the attendance mark (returns to working)

### Color Indicators

- **White**: Regular working days
- **Light Purple-Blue** (`#e8d8f0`): Employee Off days
- **Teal-Blue** (`#a8c8d8`): Employer Given Off days
- **Blue Border**: Today's date

### Managing Data

- **Clear All Data**: Located at the bottom of the page
  - Resets all employees to default list
  - Clears all attendance records
  - Requires confirmation before executing

## Design

### Color Palette

The app features a cool-toned, professional color scheme:

- **Background**: White
- **Title Section**: Light Blue (`#d0e0f0`)
- **Yearly Summary**: Darker Blue-Grey (`#d0e0e8`)
- **Monthly Summary**: Light Teal-Blue (`#e8f4f8`)
- **Employee Cards**: White with subtle borders
- **Navigation Buttons**: White
- **Employee Off**: Light Purple-Blue (`#e8d8f0`)
- **Employer Off**: Teal-Blue (`#a8c8d8`)

### Layout

- **Top Section**: "Attendance Tracker" title
- **Yearly Summary**: Year overview with employee breakdown
- **Monthly Summary**: Month navigation and employee cards
- **Bottom Section**: Clear All Data button

## Data Storage

All data is stored in the browser's localStorage:

- **Key**: `attendance_data`
- **Structure**:
  ```javascript
  {
    employees: [
      { name: 'Sarita', status: 'active' },
      { name: 'Puja', status: 'active' },
      { name: 'Jayshree', status: 'active' }
    ],
    attendance: {
      'EmployeeName|YYYY-MM-DD': 'EMPLOYEE_OFF' | 'EMPLOYER_GIVEN_OFF'
    }
  }
  ```

### Data Persistence

- Data persists across browser sessions
- Data is specific to the browser/device
- Clearing browser data will reset the app
- No data is sent to any server

## Browser Compatibility

- ✅ Chrome/Edge (Recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

## File Structure

```
Attendance Tracker/
├── attendance.html    # Main application file (all-in-one)
└── README.md          # This file
```

## Features in Detail

### Monthly Allowance System

- Each employee gets **2 days per month** of "Employee Off" allowance
- Unused days **carry forward** indefinitely
- "Employer Given Off" days do not count toward the allowance
- Balance is automatically calculated and enforced

### Calendar View

- **Interactive calendar** for each employee
- **Click dates** to mark attendance
- **Visual indicators** for different status types
- **Today indicator** with blue border
- **Month navigation** to view past and current months

### Yearly Overview

- **Aggregated statistics** for the entire year
- **Per-employee breakdown** showing:
  - Employee Off count
  - Employer Off count
- **Real-time updates** as attendance is marked

## Customization

### Changing Default Employees

Edit the `loadData()` function in `attendance.html`:

```javascript
state.employees = [
    { name: 'Your Employee 1', status: 'active' },
    { name: 'Your Employee 2', status: 'active' },
    { name: 'Your Employee 3', status: 'active' }
];
```

### Changing Monthly Allowance

Edit the allowance calculation in the `calculateBalance()` function. Currently set to 2 days per month.

### Modifying Colors

All colors are defined in the `<style>` section at the top of `attendance.html`. Search for color codes (e.g., `#e8d8f0`) to customize.

## Troubleshooting

### Data Not Saving

- Check browser console for errors (F12)
- Ensure localStorage is enabled in your browser
- Try clearing browser cache and reloading

### Calendar Not Showing

- Verify JavaScript is enabled
- Check browser console for errors
- Ensure you're viewing a month in the current year

### Colors Not Displaying Correctly

- Clear browser cache
- Ensure CSS is loading properly
- Check for browser extensions that might interfere

## Privacy & Security

- **100% Local**: All data stays in your browser
- **No Tracking**: No analytics or external requests
- **No Backend**: No server communication
- **Offline Capable**: Works without internet connection

## Future Enhancements

Potential features for future versions:
- Export data to CSV/Excel
- Multiple years support
- Custom employee fields
- Backup/restore functionality
- Print-friendly views

## License

This is an internal tool. Use and modify as needed for your business.

## Support

For issues or questions:
1. Check browser console for errors (F12)
2. Verify localStorage is working
3. Try clearing browser data and reloading
4. Ensure JavaScript is enabled

---

**Version**: 1.0  
**Last Updated**: 2026  
**Author**: Internal Tool

