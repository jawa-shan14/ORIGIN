# ORIGIN Database Blueprint v1.0

Status: In Progress

---

# Module 1 : Users

## Table : users

Purpose:
Stores the core account used for authentication.

Columns

- id (UUID, Primary Key)
- phone_number (VARCHAR, UNIQUE, NOT NULL)
- email (VARCHAR, UNIQUE, NULL)
- password_hash (TEXT, NULL)
- auth_provider (ENUM)
  - phone
  - google
  - apple

- account_status (ENUM)
  - active
  - suspended
  - banned

- created_at (TIMESTAMP)
- updated_at (TIMESTAMP)

---

## Table : profiles

Purpose:
Stores personal information.

Columns

- user_id (UUID, FK -> users.id)

- full_name

- profile_photo

- gender

- date_of_birth

- bio

- occupation

- college_or_company

- language

- city

- state

- country

- pincode

- trust_score

- total_rentals_given

- total_rentals_taken

- average_rating

- created_at

- updated_at

---

## Table : addresses

Purpose:
Stores user pickup locations.

Columns

- id
- user_id
- title
- address_line1
- address_line2
- city
- state
- country
- pincode
- latitude
- longitude
- is_default

---

## Table : verifications

Purpose:
Identity verification.

Columns

- id
- user_id

- aadhaar_number (encrypted)

- aadhaar_front

- aadhaar_back

- selfie

- verification_status
    pending
    approved
    rejected

- verified_at

---

## Table : devices

Purpose:
Stores logged-in devices.

Columns

- id
- user_id
- device_name
- operating_system
- app_version
- push_token
- last_login

---

## Table : sessions

Purpose:
Tracks active logins.

Columns

- id
- user_id
- access_token
- refresh_token
- expires_at
- last_activity
