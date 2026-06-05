## Data Dictionary — Apex Systems People & Workforce Analytics
*Apex Systems - All names and values are fictional*
10 tables · 35 employees · SQLite / PostgreSQL compatible

---

## Table of Contents

- [departments](#departments)
- [employees](#employees)
- [performance](#performance)
- [projects](#projects)
- [project_assignments](#project_assignments)
- [job_postings](#job_postings)
- [leave_requests](#leave_requests)
- [training_courses](#training_courses)
- [training_completions](#training_completions)
- [exit_interviews](#exit_interviews)

## Entity Relationship Summary

```
departments ──< employees >── performance
                    │
                    ├──< project_assignments >── projects
                    ├──< leave_requests
                    ├──< training_completions >── training_courses
                    ├──< job_postings
                    └──< exit_interviews
```

Key join paths:
- `employees.dept_id` → `departments.dept_id`
- `employees.manager_id` → `employees.employee_id`
- `performance.employee_id` → `employees.employee_id`
- `project_assignments.employee_id` → `employees.employee_id`
- `project_assignments.project_id` → `projects.project_id`
- `leave_requests.employee_id` → `employees.employee_id`
- `leave_requests.approved_by` → `employees.employee_id`
- `training_completions.employee_id` → `employees.employee_id`
- `training_completions.course_id` → `training_courses.course_id`
- `job_postings.dept_id` → `departments.dept_id`
- `job_postings.hired_employee_id` → `employees.employee_id`
- `exit_interviews.employee_id` → `employees.employee_id`
- `exit_interviews.conducted_by` → `employees.employee_id`

---

## Departments

Stores the seven organizational departments at Apex Systems, including their location, annual budget, and maximum headcount allocation. Used as the primary grouping dimension across nearly every dashboard page.

## Employees

The core workforce table. Every other table in the dataset links back to this one. Contains personal identifiers, role, compensation, employment status, and org placement.

## Performance

Annual performance review records. Each row is one review for one employee in one year. Scores drive bonus calculations and are the primary input for identifying top performers and flight risks.

## Projects

Internal company initiatives assigned to departments. Includes budget, status, and priority level. Used to analyze workload distribution and identify over-budget projects.

## Project_assignments

Bridge table connecting employees to projects. Tracks the role each employee plays and hours logged, making it the key table for workload and cross-department collaboration analysis.

## Job_postings

Hiring funnel data for all open and filled roles. Each row represents one job posting and tracks the full pipeline from application through hire. Key table for time-to-fill, source effectiveness, and conversion rate analysis.

## Leave_requests

All approved, denied, and pending leave requests. Covers PTO, sick leave, FMLA, bereavement, and unpaid leave. Used to analyze absence patterns by department, identify FMLA trends, and assess leave burden on managers.

## Training_courses

The L&D course catalog. Defines every training option available to employees — both mandatory compliance courses and optional professional development. Used as the lookup dimension for `training_completions`.

## Training_completions

Tracks which employees completed which courses, including their score and the cost incurred by the company. The bridge table between `employees` and `training_courses`, and the primary table for L&D spend and compliance gap analysis.

## Exit_interviews

Records from voluntary departure interviews. Each row represents one exiting employee's responses, including their primary reason for leaving, satisfaction ratings across four dimensions, whether they would consider returning, and where they went. Small table by design — only terminated employees have records.
