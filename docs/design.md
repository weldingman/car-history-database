# Database and API Design

This document describes the database schema and API design for the Car History Database project.

---

## Database Design

### **MongoDB Schema: Vehicle**

The `vehicle` collection stores information about individual vehicles, including their VIN, make, model, year, and associated histories.

#### **Schema Structure**
```json
{
  "vin": "string",            // Vehicle Identification Number (unique)
  "make": "string",           // Manufacturer (e.g., Toyota, Ford)
  "model": "string",          // Vehicle model (e.g., Corolla, Mustang)
  "year": "number",           // Manufacturing year
  "ownershipHistory": [
    {
      "owner": "string",      // Owner's name
      "from": "date",         // Date ownership started
      "to": "date"            // Date ownership ended (null if current)
    }
  ],
  "repairRecords": [
    {
      "date": "date",         // Repair date
      "details": "string",    // Repair description
      "cost": "number"        // Repair cost (optional)
    }
  ],
  "damageRecords": [
    {
      "date": "date",         // Date of the damage
      "details": "string",    // Damage description
      "status": "string"      // "Reported", "Repaired", or "Rebuilt"
    }
  ]
}
