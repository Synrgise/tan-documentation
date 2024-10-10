# Comprehensive Technical Handover Document: Achievement Profile Solution

## Table of Contents
1. [Project Overview](#1-project-overview)
2. [System Architecture](#2-system-architecture)
3. [Technology Stack](#3-technology-stack)
4. [Installation Guide](#4-installation-guide)
5. [Admin Features and Functions](#5-admin-features-and-functions)
6. [Scoring System](#6-scoring-system)
7. [Report Generation](#7-report-generation)
8. [Maintenance and Version Control](#8-maintenance-and-version-control)
9. [Database Structure](#9-database-structure)
10. [Security Considerations](#10-security-considerations)
11. [Testing and Quality Assurance](#11-testing-and-quality-assurance)
12. [Known Issues and Limitations](#12-known-issues-and-limitations)
13. [Support and Contact Information](#13-support-and-contact-information)
14. [Database Schema Details](#14-database-schema-details)

## 1. Project Overview

### 1.1 Project Specifications
- **Project Name**: Achievement Profile Solution
- **Version**: Laravel 5.6
- **Database**: MySQL 5.7+
- **Admin Backend**: Laravel Voyager
- **PHP Version**: 7.x

### 1.2 Project Description
The Achievement Profile Solution is a sophisticated behavioral assessment platform designed to empower administrators in setting up, managing, and analyzing participant assessments. Key features include:

- Intuitive admin interface for assessment management
- Participant registration and profile management
- Complex scoring algorithm for behavioral analysis
- Dynamic report generation based on assessment results
- PDF and HTML report formats

### 1.3 Key Components
1. Admin Dashboard (Laravel Voyager)
2. Participant Interface
3. Assessment Engine
4. Scoring Service
5. Report Generation Service
6. PDF Generation Module (dompdf)

## 2. System Architecture

### 2.1 High-Level Architecture
The Achievement Profile Solution follows a typical Laravel MVC architecture:

```
[Client Browsers] <-> [Web Server (Apache/Nginx)] <-> [Laravel Application]
                                                       |
                                                       |- [Controllers]
                                                       |- [Models]
                                                       |- [Views]
                                                       |- [Services]
                                                       |
                                                       <-> [MySQL Database]
```

### 2.2 Key Directories and Files
```
achievement-profile/
├── app/
│   ├── Http/
│   │   └── Controllers/
│   ├── Models/
│   └── Services/
│       ├── ScoringService.php
│       └── ReportService.php
├── config/
├── database/
│   ├── migrations/
│   └── seeds/
├── public/
├── resources/
│   └── views/
│       └── reports/
├── routes/
│   └── web.php
├── storage/
└── tests/
```

### 2.3 Request Lifecycle
1. HTTP request received by web server
2. Request handed to public/index.php
3. Request processed by Laravel routing (routes/web.php)
4. Appropriate controller method invoked
5. Controller interacts with models/services as needed
6. View rendered and returned as HTTP response

## 3. Technology Stack

### 3.1 Backend
- **Framework**: Laravel 5.6
- **PHP Version**: 7.x
- **Database**: MySQL 5.7+
- **ORM**: Eloquent

### 3.2 Frontend
- **Templating Engine**: Blade
- **CSS Framework**: Bootstrap 4
- **JavaScript**: jQuery

### 3.3 Admin Panel
- **Package**: Laravel Voyager

### 3.4 Additional Libraries
- **PDF Generation**: dompdf
- **Charting**: Chart.js

### 3.5 Development Tools
- **Version Control**: Git
- **Dependency Management**: Composer
- **Task Runner**: Laravel Mix (Webpack)

## 4. Installation Guide

### 4.1 Prerequisites
Ensure the following are installed on your system:
- PHP 7.x
- Composer
- MySQL 5.7+
- Node.js and NPM (for frontend asset compilation)
- Git

### 4.2 Step-by-Step Installation

1. Clone the repository:
   ```
   git clone https://github.com/your-org/achievement-profile.git
   cd achievement-profile
   ```

2. Install PHP dependencies:
   ```
   composer install
   ```

3. Install JavaScript dependencies:
   ```
   npm install
   ```

4. Create environment file:
   ```
   cp .env.example .env
   ```

5. Generate application key:
   ```
   php artisan key:generate
   ```

6. Configure database in .env file:
   ```
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=achievement_profile
   DB_USERNAME=your_username
   DB_PASSWORD=your_password
   ```

7. Run database migrations and seed:
   ```
   php artisan migrate --seed
   ```

8. Install Voyager admin panel:
   ```
   php artisan voyager:install
   ```

9. Create admin user:
   ```
   php artisan voyager:admin your@email.com --create
   ```

10. Compile assets:
    ```
    npm run dev
    ```

11. Start the development server:
    ```
    php artisan serve
    ```

12. Access the application at `http://localhost:8000` and the admin panel at `http://localhost:8000/admin`

### 4.3 Deployment Considerations
- Use a process manager like Supervisor to keep the Laravel queue worker running
- Configure your web server (Apache/Nginx) to serve the application from the `public` directory
- Ensure proper file permissions are set, especially for storage and bootstrap/cache directories
- Use environment-specific .env files for different deployment environments


## 5. Admin Features and Functions

### 5.1 Accessing Admin Panel
- The admin panel is accessible via the Partner Portal interface.
- Log in using your credentials to access the dashboard.

### 5.2 Key Admin Functions

The dashboard provides an overview of key metrics and quick access to main features:

#### 5.2.1 Managing Users
- The dashboard displays the total number of users (21 in the screenshot).
- To view or manage users, click the "View All Users" button.

#### 5.2.2 Managing Participants
- The total number of participants (5390) is shown on the dashboard.
- Access the full list of participants by clicking "View All Participants".

#### 5.2.3 Managing Organizations
- The dashboard shows the total number of organizations (333).
- To view or manage organizations, click "View All Organisations".

#### 5.2.4 Managing Teams
- The total number of teams (422) is displayed on the dashboard.
- Access team management by clicking "View All Teams".

### 5.3 Navigation Menu

The left sidebar provides quick access to various sections:

- Dashboard
- Organisations
- Participants
- Teams
- Users
- Reports (including SCO Report, Monthly Report, and Yearly Report)
- Resources
- Contact Requests
- Administration tools (ReportsManager, Applications, Scenarios, Sections, Questions, Choices)
- System configuration options

### 5.4 User Profile

- The user's name and email are displayed in the top-left corner.
- A logout option is available in the top-right corner.

This admin interface provides a comprehensive overview of the system's key components and allows for easy navigation between different management areas. The dashboard's summary cards offer quick insights into the system's usage and scale.

## 6. Scoring System

### 6.1 Scoring Service Overview
The scoring system is implemented as per the detailed requirements of the Achievement Process. These requirements would need to be covered in detail


## 7. Report Generation

### 7.1 Report Service Overview
The report generation is  implemented as per the detailed requirements of the Achievement Process. These requirements would need to be covered in detail


## 8. Maintenance and Version Control

### 8.1 Git Workflow
We use Git Flow for version control:
- `main` branch for production releases
- `develop` branch for ongoing development
- Feature branches for new features
- Release branches for preparing new releases

### 8.2 Deployment Process
1. Merge feature branches into `develop`
2. Create a release branch from `develop`
3. Perform testing on release branch
4. Merge release branch into `main` and tag with version number
5. Deploy `main` branch to production

### 8.3 Database Backups
- Daily automated backups using Laravel's backup package
- Store backups off-site (e.g., AWS S3)
- Regularly test backup restoration process

### 8.4 Updating Dependencies
Regularly update Laravel and other dependencies:
1. Update `composer.json` and `package.json`
2. Run `composer update` and `npm update`
3. Test thoroughly after updates
4. Commit updated lock files

### 8.5 Monitoring and Logging
- Use Laravel's built-in logging, configured in `config/logging.php`
- Consider integrating with a log management service (e.g., Papertrail, Loggly)
- Monitor server resources and database performance

## 9. Database Structure

### 9.1 Key Tables
- `participants`: Stores participant information
- `assessments`: Contains assessment structures
- `questions`: Stores individual assessment questions
- `responses`: Records participant responses to questions
- `scores`: Stores calculated scores
- `reports`: Maintains generated report metadata

### 9.2 Important Relationships
- Participant has many Assessments
- Assessment has many Questions
- Participant has many Responses
- Participant has many Scores
- Participant has many Reports

### 9.3 Indexing Strategy
Ensure proper indexing for performance:
- Index foreign key columns (e.g., `participant_id`, `assessment_id`)
- Index frequently queried columns (e.g., `email` in participants table)

### 9.4 Data Migration
For major schema changes:
1. Create a new migration file: `php artisan make:migration add_column_to_table`
2. Implement `up()` and `down()` methods
3. Run migration: `php artisan migrate`

## 10. Security Considerations

### 10.1 Authentication
- Uses Laravel's built-in authentication system
- Admin authentication handled by Voyager

### 10.2 Authorization
- Implement policies for fine-grained access control
- Use middleware to protect routes

### 10.3 Data Protection
- Use Laravel's encryption features for sensitive data
- Implement proper input validation and sanitization
- Use prepared statements (default in Laravel) to prevent SQL injection

### 10.4 CSRF Protection
- Laravel's CSRF protection is enabled by default
- Ensure `@csrf` directive is used in forms

### 10.5 API Security (if applicable)
- Use Laravel Passport or JWT for API authentication
- Rate limiting to prevent abuse

### 10.6 File Uploads
- Validate file types and sizes
- Store uploaded files outside of web root
- Use Laravel's storage system for file management

## 11. Testing and Quality Assurance

### 11.1 Testing Framework
- PHPUnit for unit and feature tests
- Laravel Dusk for browser testing

### 11.2 Running Tests
Execute tests with:
```
php artisan test
```

### 11.4 Continuous Integration
- Use a CI/CD tool (e.g., Jenkins, GitLab CI, GitHub Actions)
- Configure CI to run tests on every push
- Set up automated deployments for successful test runs

## 12. Known Issues and Limitations

- PDF generation can be slow for reports with many graphics
- Limited support for concurrent assessment taking (potential database locking issues)


## 13. Support and Contact Information

- Technical Support: xen@synrgise.com / sujith@synrgise.com

## 14. Database Schema Details

### Tables
1. [achievement_prefs](#achievement_prefs)
2. [achievement_stages](#achievement_stages)
3. [achievement_steps](#achievement_steps)
4. [admin_pass_resets](#admin_pass_resets)
5. [applications](#applications)
6. [business_partner_users](#business_partner_users)
7. [business_partners](#business_partners)
8. [choices](#choices)
9. [contact_requests](#contact_requests)
10. [countries](#countries)
11. [licenses](#licenses)
12. [messages](#messages)
13. [missing_contributions](#missing_contributions)
14. [organisation_industries](#organisation_industries)
15. [organisation_links](#organisation_links)
16. [organisation_links_types](#organisation_links_types)
17. [organisations](#organisations)
28. [participant_ndfs](#participant_ndfs)
19. [participant_sections](#participant_sections)
20. [participants](#participants)
21. [perfomance_improvements](#perfomance_improvements)
22. [processes](#processes)
23. [questions](#questions)
24. [reminders](#reminders)
25. [reminders_sent](#reminders_sent)
26. [report_feedbacks](#report_feedbacks)
27. [report_templates](#report_templates)
28. [reportsmanager](#reportsmanager)
29. [reportsmanager_pages](#reportsmanager_pages)
30. [resource_folders](#resource_folders)
31. [resources](#resources)
32. [scenario_applications](#scenario_applications)
33. [scenario_sections](#scenario_sections)
34. [scenarios](#scenarios)
35. [sections](#sections)
36. [team_organisations](#team_organisations)
37. [team_participants](#team_participants)
38. [team_users](#team_users)
39. [teams](#teams)
40. [users](#users)

### achievement_prefs

Stores information about achievement preferences.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the achievement preference |
| pref_cd | varchar(3) | | Preference code |
| pref_name | varchar(200) | | Preference name |
| pref_rank | tinyint(4) | | Preference rank |
| team_pref | varchar(100) | | Team preference |
| team_exp | varchar(100) | | Team experience |
| team_pref_desc | text | | Team preference description |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |

### achievement_stages

Stores information about achievement stages.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the achievement stage |
| stage_cd | varchar(3) | | Stage code |
| stage_name | varchar(200) | | Stage name |
| stage_seq | tinyint(4) | | Stage sequence |
| hmtl_color_code | varchar(7) | | HTML color code |
| pref_desc | text | | Preference description |
| pref_details_title | varchar(100) | | Preference details title |
| pref_details | text | | Preference details |
| pref_details_focus | varchar(100) | | Preference details focus |
| pref_details_close | text | | Preference details close |
| pref_chars | varchar(255) | | Preference characteristics |
| comm_prefs | text | | Communication preferences |
| comm_statement | text | | Communication statement |
| comm_closing | text | | Communication closing |
| comm_matching | text | | Communication matching |
| comm_mismatch | mediumtext | | Communication mismatch |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |

### achievement_steps

Stores information about achievement steps.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the achievement step |
| step_cd | varchar(3) | | Step code |
| step_name | varchar(200) | | Step name |
| step_seq | tinyint(4) | | Step sequence |
| achievement_stage_id | int(11) | | Foreign key to achievement_stages table |
| hmtl_color_code | varchar(10) | | HTML color code |
| pref_desc_title | varchar(200) | | Preference description title |
| pref_desc | text | | Preference description |
| pref_desc_close | varchar(255) | | Preference description close |
| low_desc | text | | Low description |
| low_statement | varchar(255) | | Low statement |
| low_close | varchar(255) | | Low close |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |

### admin_pass_resets

Stores information about admin password resets.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(11) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the admin password reset |
| user_id | int(11) | | Foreign key to users table |
| email | varchar(255) | | Email address |
| token | varchar(255) | | Reset token |
| created_at | datetime | | Creation timestamp |
| updated_at | datetime | | Last update timestamp |

### applications

Stores information about applications.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the application |
| name | varchar(250) | NOT NULL | Application name |
| description | text | | Application description |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |
| deleted_at | timestamp | | Deletion timestamp (for soft deletes) |
| app_icd | varchar(100) | | Application ICD |

### business_partner_users

Links business partners to users.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the business partner user link |
| business_partner_id | int(11) | | Foreign key to business_partners table |
| user_id | int(11) | | Foreign key to users table |

### business_partners

Stores information about business partners.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the business partner |
| company_name | varchar(255) | | Company name |
| primary_contact | varchar(255) | | Primary contact name |
| contact_position | varchar(255) | | Contact position |
| contact_tel | varchar(255) | | Contact telephone number |
| contact_email | varchar(255) | | Contact email address |
| status | varchar(255) | NOT NULL | Status of the business partner |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |
| deleted_at | timestamp | | Deletion timestamp (for soft deletes) |
| logo | varchar(255) | | Logo file path |

### choices

Stores information about choices for questions.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the choice |
| choice_txt | varchar(250) | NOT NULL | Choice text |
| choice_seq | tinyint(4) | | Choice sequence |
| question_id | int(11) | | Foreign key to questions table |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |
| score_id | int(11) | | Foreign key to scores table |
| AchvmntStepID | int(11) | | Foreign key to achievement_steps table |
| QN_ScoreTypeID | int(11) | | Foreign key to score types table |
| QN_SectionID | int(11) | | Foreign key to sections table |
| AchvmntStageID | int(11) | | Foreign key to achievement_stages table |
| AchvmntPrefID | int(11) | | Foreign key to achievement_prefs table |
| teamworking | tinyint(1) | | Teamworking flag (1 = Preference, 2 = Experience) |

### contact_requests

Stores information about contact requests.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the contact request |
| subject | varchar(255) | NOT NULL | Subject of the contact request |
| fullname | varchar(255) | | Full name of the requester |
| company | varchar(255) | | Company name |
| message | text | | Message content |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |
| email | varchar(255) | | Email address of the requester |

### countries

Stores information about countries.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(11) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the country |
| name | varchar(255) | | Country name |
| dial | varchar(255) | | Country dial code |
| continent_id | int(11) | | Foreign key to continents table |
| iso | varchar(11) | | ISO code |
| iso_2 | varchar(11) | | ISO-2 code |
| continent_short | varchar(11) | | Continent short code |
| continent_short_2 | varchar(11) | | Alternate continent short code |
| country_short | varchar(11) | | Country short code |

### licenses

Stores information about licenses.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the license |
| oranisation_id | int(11) | | Foreign key to organisations table |
| number_of_keys | int(11) | | Number of license keys |
| keys_used | int(11) | | Number of keys used |
| expirty_date | date | | Expiry date of the license |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |
| level | tinyint(4) | | License level |

### messages

Stores information about messages.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the message |
| message_name | varchar(200) | | Message name |
| message_body | text | | Message body content |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |

### missing_contributions

Stores information about missing contributions.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(11) | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the missing contribution |
| team_id | int(11) | | Foreign key to teams table |
| assessing_reality | tinyint(1) | | Assessing reality flag |
| driving_onward | tinyint(1) | | Driving onward flag |
| planning_ahead | tinyint(1) | | Planning ahead flag |
| enabling_action | tinyint(1) | | Enabling action flag |
| implementing_plans | tinyint(1) | | Implementing plans flag |
| created_by | int(11) | | Foreign key to users table (creator) |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |

### organisation_industries

Stores information about organisation industries.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(11) | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the organisation industry |
| name | varchar(255) | | Industry name |

### organisation_links

Stores links between organisations.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(11) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the organisation link |
| organisation_1_id | int(11) | | Foreign key to organisations table (first organisation) |
| organisation_2_id | int(11) | | Foreign key to organisations table (second organisation) |
| created_at | datetime | | Creation timestamp |
| updated_at | datetime | | Last update timestamp |

### organisation_links_types

Stores types of organisation links.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(11) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the organisation link type |
| organisation_type_id | int(11) | | Foreign key to organisation types table |
| desc | varchar(255) | | Description of the link type |
| org1_org2_desc | varchar(255) | | Description of the relationship from org1 to org2 |
| org2_org1_desc | varchar(255) | | Description of the relationship from org2 to org1 |

### organisations

Stores information about organisations.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the organisation |
| company_name | varchar(250) | NOT NULL | Company name |
| address | text | | Company address |
| tel_number | varchar(100) | | Telephone number |
| website | varchar(250) | | Website URL |
| email | varchar(250) | | Email address |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |
| primarycontact | varchar(255) | | Primary contact name |
| contactposition | varchar(255) | | Contact position |
| description | text | | Organisation description |
| industry | varchar(255) | | Industry |
| business_partner_id | int(11) | | Foreign key to business_partners table |
| type_id | int(11) | | Foreign key to organisation types table |
| location | varchar(255) | | Location |
| town | varchar(255) | | Town |
| city | varchar(255) | | City |
| comments | text | | Comments |
| user_id | int(11) | | Foreign key to users table |
| country_id | int(11) | | Foreign key to countries table |
| org_industry_id | int(11) | | Foreign key to organisation_industries table |
| logo | varchar(255) | | Logo file path |

### participant_ndfs

Stores information about participant NDFs (Normal Distribution Function).

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the participant NDF |
| stage_normal_cq | int(11) | | Normal stage CQ score |
| stage_normal_do | int(11) | | Normal stage DO score |
| stage_normal_pa | int(11) | | Normal stage PA score |
| stage_normal_ea | int(11) | | Normal stage EA score |
| stage_normal_cp | int(11) | | Normal stage CP score |
| stage_high_cq | int(11) | | High stage CQ score |
| stage_high_do | int(11) | | High stage DO score |
| stage_high_pa | int(11) | | High stage PA score |
| stage_high_ea | int(11) | | High stage EA score |
| stage_high_cp | int(11) | | High stage CP score |
| step_normal_mp | int(11) | | Normal step MP score |
| step_normal_am | int(11) | | Normal step AM score |
| step_normal_er | int(11) | | Normal step ER score |
| step_normal_dc | int(11) | | Normal step DC score |
| step_normal_da | int(11) | | Normal step DA score |
| step_normal_ii | int(11) | | Normal step II score |
| step_normal_po | int(11) | | Normal step PO score |
| step_normal_ce | int(11) | | Normal step CE score |
| step_normal_mm | int(11) | | Normal step MM score |
| step_normal_ra | int(11) | | Normal step RA score |
| step_normal_pi | int(11) | | Normal step PI score |
| step_normal_ns | int(11) | | Normal step NS score |
| step_normal_sp | int(11) | | Normal step SP score |
| step_normal_ef | int(11) | | Normal step EF score |
| step_normal_st | int(11) | | Normal step ST score |
| step_high_mp | int(11) | | High step MP score |
| step_high_am | int(11) | | High step AM score |
| step_high_er | int(11) | | High step ER score |
| step_high_dc | int(11) | | High step DC score |
| step_high_da | int(11) | | High step DA score |
| step_high_ii | int(11) | | High step II score |
| step_high_po | int(11) | | High step PO score |
| step_high_ce | int(11) | | High step CE score |
| step_high_mm | int(11) | | High step MM score |
| step_high_ra | int(11) | | High step RA score |
| step_high_pi | int(11) | | High step PI score |
| step_high_ns | int(11) | | High step NS score |
| step_high_sp | int(11) | | High step SP score |
| step_high_ef | int(11) | | High step EF score |
| step_high_st | int(11) | | High step ST score |
| comm_normal_cq | int(11) | | Normal communication CQ score |
| comm_normal_do | int(11) | | Normal communication DO score |
| comm_normal_pa | int(11) | | Normal communication PA score |
| comm_normal_ea | int(11) | | Normal communication EA score |
| comm_normal_cp | int(11) | | Normal communication CP score |
| comm_high_cq | int(11) | | High communication CQ score |
| comm_high_do | int(11) | | High communication DO score |
| comm_high_pa | int(11) | | High communication PA score |
| comm_high_ea | int(11) | | High communication EA score |
| comm_high_cp | int(11) | | High communication CP score |
| contribution_awareness | int(11) | | Contribution awareness score |
| team_pref_score | int(11) | | Team preference score |
| team_exp_score | int(11) | | Team experience score |
| team_pref | varchar(100) | | Team preference |
| team_exp | varchar(100) | | Team experience |
| participant_id | int(11) | | Foreign key to participants table |
| campaign_id | int(11) | | Foreign key to campaigns table |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |

### participant_sections

Stores information about participant sections.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the participant section |
| participant_id | int(11) | | Foreign key to participants table |
| section_id | int(11) | | Foreign key to sections table |
| campaign_id | int(11) | | Foreign key to campaigns table |
| status | varchar(47) | | Status of the participant section |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |
| result | text | | Result of the section |
| json_result | json | | JSON-formatted result of the section |
| started_at | timestamp | | Start timestamp of the section |

### participants

Stores information about participants.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the participant |
| title | varchar(100) | | Participant's title |
| firstname | varchar(255) | | First name |
| initials | varchar(100) | | Initials |
| lastname | varchar(255) | | Last name |
| mobile_number | varchar(200) | | Mobile number |
| email | varchar(200) | | Email address |
| team_id | int(11) | | Foreign key to teams table |
| organisation_id | int(11) | | Foreign key to organisations table |
| access_code | varchar(255) | | Access code |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |
| deleted_at | timestamp | | Deletion timestamp (for soft deletes) |
| application_id | int(11) | | Foreign key to applications table |
| process_id | int(11) | | Foreign key to processes table |
| report_feedback_id | int(11) | | Foreign key to report_feedbacks table |
| reminder_id | int(11) | | Foreign key to reminders table |
| facilitator_id | int(11) | | Foreign key to users table (facilitator) |
| due_date | date | | Due date |
| business_partner_id | int(11) | | Foreign key to business_partners table |
| comments | longtext | | Comments |
| job_function | varchar(255) | | Job function |

### perfomance_improvements

Stores information about performance improvements.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(11) | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the performance improvement |
| blackhole_cutoff | int(11) | | Black hole cutoff value |
| deepbog_cutoff | int(11) | | Deep bog cutoff value |
| mp_checkbox | tinyint(1) | | MP checkbox flag |
| am_checkbox | tinyint(1) | | AM checkbox flag |
| el_checkbox | tinyint(1) | | EL checkbox flag |
| vf_checkbox | tinyint(1) | | VF checkbox flag |
| fd_checkbox | tinyint(1) | | FD checkbox flag |
| tb_checkbox | tinyint(1) | | TB checkbox flag |
| co_checkbox | tinyint(1) | | CO checkbox flag |
| td_checkbox | tinyint(1) | | TD checkbox flag |
| st_checkbox | tinyint(1) | | ST checkbox flag |
| mr_checkbox | tinyint(1) | | MR checkbox flag |
| io_checkbox | tinyint(1) | | IO checkbox flag |
| ns_checkbox | tinyint(1) | | NS checkbox flag |
| cp_checkbox | tinyint(1) | | CP checkbox flag |
| ce_checkbox | tinyint(1) | | CE checkbox flag |
| mm_checkbox | tinyint(1) | | MM checkbox flag |
| team_id | int(11) | | Foreign key to teams table |
| created_by | int(11) | | Foreign key to users table (creator) |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |

### processes

Stores information about processes.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the process |
| name | varchar(200) | | Process name |

### questions

Stores information about questions.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the question |
| question | varchar(250) | NOT NULL | Question text |
| section_id | int(11) | | Foreign key to sections table |
| section_seq | int(11) | | Sequence within the section |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |

### reminders

Stores information about reminders.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the reminder |
| interval | varchar(100) | | Reminder interval |

### reminders_sent

Stores information about sent reminders.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(11) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the sent reminder |
| participant_id | int(11) | | Foreign key to participants table |
| reminder_id | int(11) | | Foreign key to reminders table |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |

### report_feedbacks

Stores information about report feedbacks.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the report feedback |
| name | varchar(255) | | Feedback name |

### report_templates

Stores information about report templates.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the report template |
| title | varchar(255) | | Template title |
| description | text | | Template description |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |
| template | varchar(255) | | Template file path |

### reportsmanager

Stores information about report management.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the report manager entry |
| report_name | varchar(200) | | Report name |
| report_json | longtext | | Report JSON data |
| report_html_json | longtext | | Report HTML JSON data |
| report_css_json | longtext | | Report CSS JSON data |
| report_html | longtext | | Report HTML content |
| report_css | longtext | | Report CSS content |
| organisation_id | int(11) | | Foreign key to organisations table |
| business_partner_id | int(11) | | Foreign key to business_partners table |
| connected_to | varchar(255) | | Connected entity |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |
| participant_id | varchar(11) | | Foreign key to participants table |

### reportsmanager_pages

Stores information about report manager pages.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(11) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the report manager page |
| name | varchar(255) | | Page name |
| report_id | int(11) | | Foreign key to reportsmanager table |
| report_json | longtext | | Report JSON data |
| report_html | longtext | | Report HTML content |
| report_css | longtext | | Report CSS content |
| created_at | datetime | | Creation timestamp |
| updated_at | datetime | | Last update timestamp |
| order | int(11) | | Page order |
| conditional | varchar(255) | | Conditional logic |

### resource_folders

Stores information about resource folders.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(11) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the resource folder |
| name | varchar(255) | | Folder name |
| created_at | datetime | | Creation timestamp |
| updated_at | datetime | | Last update timestamp |

### resources

Stores information about resources.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the resource |
| title | varchar(255) | | Resource title |
| file | varchar(255) | | File path |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |
| folder_id | int(11) | | Foreign key to resource_folders table |

### scenario_applications

Links scenarios to applications.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the scenario-application link |
| application_id | int(11) | | Foreign key to applications table |
| scenario_id | int(11) | | Foreign key to scenarios table |

### scenario_sections

Links scenarios to sections.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the scenario-section link |
| section_id | int(11) | | Foreign key to sections table |
| scenario_id | int(11) | | Foreign key to scenarios table |

### scenarios

Stores information about scenarios.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the scenario |
| name | varchar(250) | | Scenario name |
| description | text | | Scenario description |
| sequence | int(11) | | Sequence order |
| status | varchar(100) | | Scenario status |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |
| report_type | varchar(10) | | Report type |

### sections

Stores information about sections.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the section |
| section_cd | varchar(5) | NOT NULL | Section code |
| section2charCD | char(2) | | Two-character section code |
| name | varchar(100) | NOT NULL | Section name |
| sequence | smallint(6) | | Sequence order |
| active | tinyint(4) | | Active status |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |
| type | tinyint(4) | | Section type |
| description | text | | Section description |

### team_organisations

Links teams to organisations.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(11) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the team-organisation link |
| team_id | int(11) | | Foreign key to teams table |
| organisation_id | int(11) | | Foreign key to organisations table |
| created_at | datetime | | Creation timestamp |
| updated_at | datetime | | Last update timestamp |

### team_participants

Links teams to participants.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(11) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the team-participant link |
| team_id | int(11) | | Foreign key to teams table |
| participant_id | int(11) | | Foreign key to participants table |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |

### team_users

Links teams to users.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the team-user link |
| team_id | int(11) | | Foreign key to teams table |
| participant_id | int(11) | | Foreign key to participants table |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |

### teams

Stores information about teams.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the team |
| team_name | varchar(200) | | Team name |
| description | longtext | | Team description |
| type | varchar(255) | | Team type |
| organisation_id | int(11) | | Foreign key to organisations table |
| business_partner_id | int(11) | | Foreign key to business_partners table |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |
| facilitator_id | int(11) | | Foreign key to users table (facilitator) |

### users

Stores information about users.

| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| id | int(10) unsigned | PRIMARY KEY, AUTO_INCREMENT | Unique identifier for the user |
| role_id | int(10) unsigned | | Foreign key to roles table |
| name | varchar(255) | NOT NULL | User's full name |
| email | varchar(255) | NOT NULL, UNIQUE | User's email address |
| avatar | varchar(255) | DEFAULT 'users/default.png' | User's avatar image path |
| password | varchar(255) | NOT NULL | Encrypted password |
| remember_token | varchar(100) | | Remember me token |
| settings | text | | User settings |
| tel_number | varchar(255) | | Telephone number |
| mob_number | varchar(255) | | Mobile number |
| position | varchar(255) | | User's position |
| accreditation_level | int(11) | | Accreditation level |
| accreditation_user | int(11) | | Foreign key to users table (accreditation user) |
| accreditation_certificate | text | | Accreditation certificate details |
| copyright_agreement | text | | Copyright agreement details |
| created_at | timestamp | | Creation timestamp |
| updated_at | timestamp | | Last update timestamp |
| deleted_at | timestamp | | Deletion timestamp (for soft deletes) |
| team_id | int(11) | | Foreign key to teams table |
| organisation_id | int(11) | | Foreign key to organisations table |
| business_partner_id | int(11) | | Foreign key to business_partners table |
| logo | varchar(255) | | Logo file path |
| website | varchar(255) | | Website URL |
| company | varchar(255) | | Company name |

### Relationships

This section describes the relationships between the tables in the database schema.

1. **organisations** to **users**: One-to-Many (An organisation can have multiple users)
2. **organisations** to **teams**: One-to-Many (An organisation can have multiple teams)
3. **organisations** to **participants**: One-to-Many (An organisation can have multiple participants)
4. **teams** to **participants**: One-to-Many (A team can have multiple participants)
5. **users** to **teams**: One-to-Many (A user can be a facilitator for multiple teams)
6. **business_partners** to **organisations**: One-to-Many (A business partner can be associated with multiple organisations)
7. **business_partners** to **users**: One-to-Many (A business partner can have multiple users)
8. **applications** to **participants**: One-to-Many (An application can have multiple participants)
9. **processes** to **participants**: One-to-Many (A process can have multiple participants)
10. **report_feedbacks** to **participants**: One-to-Many (A report feedback can be associated with multiple participants)
11. **reminders** to **participants**: One-to-Many (A reminder can be associated with multiple participants)
12. **scenarios** to **applications**: Many-to-Many (through scenario_applications)
13. **scenarios** to **sections**: Many-to-Many (through scenario_sections)
14. **sections** to **questions**: One-to-Many (A section can have multiple questions)
15. **questions** to **choices**: One-to-Many (A question can have multiple choices)
16. **achievement_stages** to **achievement_steps**: One-to-Many (An achievement stage can have multiple achievement steps)
17. **participants** to **participant_sections**: One-to-Many (A participant can have multiple participant sections)
18. **participants** to **participant_ndfs**: One-to-Many (A participant can have multiple NDFs)
19. **resource_folders** to **resources**: One-to-Many (A resource folder can contain multiple resources)
20. **reportsmanager** to **reportsmanager_pages**: One-to-Many (A report can have multiple pages)
