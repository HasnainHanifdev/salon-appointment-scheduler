# Salon Appointment Scheduler

A command-line salon booking system built with **Bash** and **PostgreSQL**. Customers choose a service, enter their phone number (and name if they are new), pick a time, and the appointment is saved to the database.

Built as part of the freeCodeCamp *Relational Databases* certification.

## Features

- Numbered list of services, shown before the first prompt
- Re-shows the list if the choice is not a valid service
- Looks customers up by phone number and only asks for a name if they are new
- Saves customers and appointments in PostgreSQL
- Prints a confirmation message after booking

## Tech Stack

- Bash
- PostgreSQL (`psql`)

## Database Design

| Table | Columns |
|---|---|
| `customers` | `customer_id` (PK), `phone` (unique), `name` |
| `services` | `service_id` (PK), `name` |
| `appointments` | `appointment_id` (PK), `customer_id` (FK), `service_id` (FK), `time` |

## Setup

1. Make sure PostgreSQL is running.
2. Rebuild the database from the dump:

   ```bash
   psql -U postgres < salon.sql
   ```

3. Make the script executable:

   ```bash
   chmod +x salon.sh
   ```

## Usage

```bash
./salon.sh
```

## Possible Improvements

- Validate phone number format
- Validate time input
- Prevent double-booking of the same time slot
- Escape user input before using it in SQL queries
