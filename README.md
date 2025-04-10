# Landlord Developer Technical Assessment

<p align="center"><a href="https://uselandlord.com" target="_blank"><img src="https://uselandlord.com/wp-content/uploads/2025/04/landlordlogo.png" width="400" alt="Landlord Logo"></a></p>

- [Landlord Developer Technical Assessment](#landlord-developer-technical-assessment)
   * [Position Overview](#position-overview)
   * [Application Process](#application-process)
      + [Environment Setup](#environment-setup)
         - [Prerequisites](#prerequisites)
         - [Setup Instructions](#setup-instructions)
         - [Next Steps](#next-steps)
         - [Accessing the Application](#accessing-the-application)
      + [Submission Instructions](#submission-instructions)
   * [Technical Assessment Tasks](#technical-assessment-tasks)
      + [Basic Tasks (1 Point Each)](#basic-tasks-1-point-each)
         - [1. Success Notification Button](#1-success-notification-button)
         - [2. Page Toggle](#2-page-toggle)
         - [3. Unit Data Table](#3-unit-data-table)
         - [4. Unit Size Filter](#4-unit-size-filter)
      + [Intermediate Tasks (3 Points Each)](#intermediate-tasks-3-points-each)
         - [5. Metric Converter](#5-metric-converter)
         - [6. Unit Model & Database](#6-unit-model-database)
         - [7. Prorated Rent Calculator](#7-prorated-rent-calculator)
      + [Advanced Tasks (5 Points Each)](#advanced-tasks-5-points-each)
         - [8. Unit Management CRUD Interface](#8-unit-management-crud-interface)
         - [9. Rent Increase Planning Tool](#9-rent-increase-planning-tool)
   * [Example Data](#example-data)

## Position Overview

Landlord is well-funded and is looking for extremely talented full stack developers to pioneer a software that is eliminating property inequality. The mega rich feel comfortable owning property because they have dozens of property managers who can manage their property investments for them. Landlord software currently manages thousands of tenants with a built in AI property manager that gives the average property owner the same level of property management support that a billionaire would have. People want to be property owners, not property managers. We ENCOURAGE the use of AI in our technical interview because you'll be using it in your job. 

(<a href="https://claude.ai"><img src="https://img.shields.io/badge/-Try%20Claude-7A56E3?logo=anthropic&logoColor=white" align="center"/></a>, <a href="https://www.deepseek.com/"><img src="https://img.shields.io/badge/-Try%20DeepSeek-006AFF?logo=deepseek&logoColor=white" align="center"/></a>)
Expect to have intense, driven, interesting co-workers.

We don't care if you didn't go to university, or what languages you've coded in before, or where you live/work from.

**The only thing we care about is that you can produce exceptional code and we will pay you well for doing so.**
**We encourage you to use AI tools during your job and during the technical test below.**

## Application Process

1. Setup the environment
2. Setup a PDF to track your time stamps for how long you spend on each task
3. Complete as many technical tasks as you can
4. Submit your application to `applytodeeprent@gmail.com` according to the [Submission Instructions](#submission-instructions)

### Environment Setup

Installation done with a Macbook Air with M1 chip.
If you have issues installing, we highly recommend consulting:
<a href="https://claude.ai">
<img src="https://img.shields.io/badge/-Claude-000000?logo=anthropic&logoColor=white"/>
</a>
<a href="https://chat.openai.com">
<img src="https://img.shields.io/badge/-ChatGPT-412991?logo=openai&logoColor=white"/>
</a>

#### Prerequisites
- Git
- Docker Desktop and Docker Compose (<a href="https://www.docker.com/products/docker-desktop/"><img src="https://img.shields.io/badge/-Download%20DockerDesktop-blue?logo=docker&logoColor=white" align="center"/></a>)
- Terminal access
- *optional DBeaver Desktop for database management (<a href="https://dbeaver.io/download/"><img src="https://img.shields.io/badge/-Download%20DBeaver-blue?logo=dbeaver&logoColor=black" align="center"/></a>)

#### Setup Instructions

1. Clone the repository
```bash
git clone https://github.com/RedH11/show-your-skills-landlord.git
```

2. Navigate to the project directory
```bash
cd show-your-skills-landlord
```

3. Start Docker containers
```bash
docker-compose up -d
```

4. Set proper permissions
```bash
chmod -R 777 storage bootstrap/cache
```

5. Install PHP dependencies
```bash
docker-compose exec app composer install
```

6. Create environment file
```bash
cp .env.example .env
```

7. Generate application key
```bash
docker-compose exec app php artisan key:generate
```

#### Next Steps
After completing these steps, your development environment should be ready. Make sure all services are running properly by checking Docker container status:
```bash
docker-compose ps
```

#### Accessing the Application
Once all services are running, you can access the application by opening your web browser and navigating to:
```
http://localhost:8000
```

### Submission Instructions

Email the following to `applytodeeprent@gmail.com`<br>
**Please ensure that you correctly add up the points, the tasks have different point values based on their difficulty**

**Subject:** [POINT TOTAL] - [TIME SPENT ON TASKS] - [FULL NAME]

**Required Contents:**
1. PDF containing a list the tasks you completed with time stamps in order of completion and include screenshots of your result for the task
2. Code package (ZIP format)
3. A good phone number we can text you at

## Technical Assessment Tasks

RULES:
- You are allowed to make more files
- You are allowed to use additional libraries

### Basic Tasks (1 Point Each)

#### 1. Success Notification Button
**Requirements:**
- Complete this task using the files called `success-notification-button.blade.php` / `SuccessNotificationButton.php`
- Create a button
- When the button is clicked it should show some form of loading animation
- After two seconds of loading, something that says "Success" should pop up on the screen

#### 2. Page Toggle
**Requirements:**
- Complete this task using the files called `page-toggle-one.blade.php` / `PageToggleOne.php` and `page-toggle-two.blade.php` / `PageToggleTwo.php`
- Make one page have a white background and the other have a black background
- Make a button that says "Make background dark" that navigates the user to the dark page from the light page
- Make a button that says "Make background light" that navigates the user to the light page from the dark page

#### 3. Unit Data Table
**Requirements:**
- Complete this task using the files called `unit-data-table.blade.php` / `UnitDataTable.php`
- Create a table using provided test data from `/example/unit-data.json`
- Sort the table by the size of the unit (smallest to largest)
- Implement search functionality that matches search input to unit name
- Add in pagination with only 3 units per page
- 
#### 4. Unit Size Filter
**Requirements:**
- Complete this task using the files called `unit-size-filter.blade.php` / `UnitSizeFilter.php`
- Use the size options from `/example/unit-data.json`
- Create a dropdown menu for the different unit sizes 
- Whatever unit size is selected in the dropdown, display the unit data for that size to the user

### Intermediate Tasks (3 Points Each)

#### 5. Metric Converter
**Requirements:**
- Complete this task using the files called `metric-converter.blade.php` / `MetricConverter.php`
- Make two input fields, one for feet and one for meters
- When typing into one input field have the other input field show the converted value (bidirectionally)
- Set appropriate decimal precision for the converted values
- Add input validation to prevent invalid number entries

#### 6. Unit Model & Database
**Requirements:**
- Create a Unit model using laravel with fields for length (float), width (float), name (string), price (float), and status (string: "rented" or "available")
- Write database migrations to set up a "units" table with the proper columns for each field in the Unit model
- Add to the database seeder code that populates the database with test data from `/example/unit-data.json`

#### 7. Prorated Rent Calculator
**Requirements:**
- Complete this task using the files called `prorated-calculator.blade.php` / `ProratedCalculator.php`
- Create an interface where users can enter a move-in date and a monthly rent amount
- The calculator should include the start and end date of the proration, the price per day, and the amount of days
- Account for different month lengths and leap years in the calculation
- Allow the user to export a PDF of the page

### Advanced Tasks (5 Points Each)

#### 8. Unit Management CRUD Interface
**Requirements:**
- Complete this task using the files called `unit-management.blade.php` / `UnitManagement.php`
- Create an interface with the ability to Create, Read, Update, and Delete units listed in a table (like Task 3)
- Connect this table to a back-end MySQL database (like Task 6)
- Ensure all alterations show up in the units table of the database

#### 9. Rent Increase Planning Tool
**Requirements:**
- Complete this task using the files called `rent-planning.blade.php` / `RentPlanning.php`
- Assume the property makes $3,000 in rent a month
- Create a line graph that shows a representation of the aggregate rent income throughout a year (e.g. January $3k, February $6k, etc.)
- Add functionality to have the user input how much rent they would like to make total throughout the year (e.g. $desiredRent = $50,000)
- Using the $desiredRent, calculate two evenly spaced rent raises from the current day to the end of the year that would result in this desired rent amount being reached
- Show two vertical lines for when the rent raises would be complete, and when you hover over the lines show by how much the rent would be raised (in percent form)
- Display monthly revenue projections based on the planned increases

## Example Data
All referenced example data files will be provided in the repository under the `example/` directory. Each file includes sample data structures and configuration options needed to complete the tasks.
