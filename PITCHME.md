# Distributed Locking

---

### The Problem

Mautic can create duplicate records

```json zoom
{
  "id": 123,
  "global_customer_id": "713249951"
  ...
}
```

@snap[south span-100 text-gray text-08]
@[2](Mautic's internal ID)
@[3](VIN's surrogate ID)
@snapend

---

### The Problem

Blanking out values in Mautic was difficult

```
POST /api/contacts/batch/new
PUT /api/contacts/batch/edit
PATCH /api/contacts/batch/edit
```

---

### How it Works

Enter DynamoDB

```json
{
  "Id": "MauticContact267582519",
  "LockExpiration": 1592509829,
  "EventSourceDates": {
    "AmpVehicle": 1592051820
  },
  "Expiration": 1592639338
}
```

@snap[south span-100 text-gray text-08]
@[2](Identify the resource being locked)
@[3](Specify when the lock expires (in epoch seconds))
@[4-6](Extra credit: keep track of when things are updated)
@[7](When the record itself will be deleted)
@snapend

