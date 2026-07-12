# ORIGIN Marketplace Database v1.0

Status: Approved

---

# TABLE : categories

Purpose:
Stores all item categories.

Columns

- id (UUID)
- name
- icon
- description
- is_active
- created_at
- updated_at

Examples

Electronics
Fashion
Vehicles
Books
Gaming
Cameras
Sports
Tools
Musical Instruments
Home Appliances

---

# TABLE : items

Purpose:
Stores every rentable item.

Columns

- id (UUID)

- owner_id (FK -> users.id)

- category_id (FK -> categories.id)

- title

- description

- rental_price

- security_deposit

- minimum_rental_days

- maximum_rental_days

- condition
    New
    Like New
    Good
    Fair

- purchase_year

- brand

- model

- current_value

- pickup_address_id

- availability_status
    Available
    Booked
    Maintenance
    Hidden

- approval_status
    Pending
    Approved
    Rejected

- created_at

- updated_at

---

# TABLE : item_images

Purpose:
Stores multiple images.

Columns

- id
- item_id
- image_url
- display_order
- created_at

---

# TABLE : item_availability

Purpose:
Stores blocked dates.

Columns

- id
- item_id
- start_date
- end_date
- reason

Reason Examples

Booked

Maintenance

Owner Blocked

---

# TABLE : favorites

Purpose:
Users save items.

Columns

- id
- user_id
- item_id
- created_at
