# Distributed Locking

---

### The Problem

Mautic can create duplicate records

Example:
```json zoom
{
  "id": 123,
  "global_customer_id": "713249951"
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
@[2](You can step-and-ZOOM into fenced-code blocks, source files, and Github GIST.)
@[3](Using GitPitch live code presenting with optional annotations.)
@[4-6](This means no more switching between your slide deck and IDE on stage.)
@snapend

