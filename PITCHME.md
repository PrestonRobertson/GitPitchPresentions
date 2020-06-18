# Distributed Locking

---

### The Problem

Mautic can create duplicate records

Example:
```json
{
  "id": 123,
  "global_customer_id": "713249951"\
  ...
}
```

---

### The Problem

Blanking out values in Mautic was difficult

```
POST /api/contacts/batch/new
PUT /api/contacts/batch/edit
PATCH /api/contacts/batch/edit
```

### How it Works

Enter DynamoDB

```json
{
  "EventSourceDates": {
    "AmpVehicle": 1592051820
  },
  "Expiration": 1592639338,
  "Id": "MauticContact267582519",
  "LockExpiration": 0
}
```
