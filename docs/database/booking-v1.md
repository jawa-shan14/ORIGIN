# ORIGIN Booking Database v1.0

Status: Approved

---

# TABLE : bookings

Purpose:
Stores every rental booking.

Columns

- id (UUID)

- booking_number (Unique)

- item_id (FK -> items.id)

- owner_id (FK -> users.id)

- borrower_id (FK -> users.id)

- start_date

- end_date

- total_days

- rental_amount

- security_deposit

- platform_fee

- total_amount

- booking_status

Requested

Accepted

Rejected

Payment Pending

Confirmed

Ready For Pickup

Rental Active

Return Requested

Inspection

Completed

Cancelled

Disputed

Late Return

- cancellation_reason

- created_at

- updated_at

---

# TABLE : booking_status_history

Purpose:
Tracks every booking status change.

Columns

- id

- booking_id

- previous_status

- new_status

- changed_by

Owner

Borrower

System

Admin

- remarks

- created_at

---

# TABLE : pickup_otps

Purpose:
Pickup verification.

Columns

- id

- booking_id

- otp_code

- expires_at

- verified_at

- created_at

---

# TABLE : return_otps

Purpose:
Return verification.

Columns

- id

- booking_id

- otp_code

- expires_at

- verified_at

- created_at

---

# TABLE : booking_extensions

Purpose:
Borrower requests extra rental days.

Columns

- id

- booking_id

- requested_end_date

- additional_amount

- owner_response

Pending

Accepted

Rejected

- created_at
