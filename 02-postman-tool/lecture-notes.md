# Postman & API Fundamentals: Theory Notes

### Resources
* **Downloads:** [Postman Desktop](https://www.postman.com/downloads/)
* **Documentation:** [Restful Booker API Doc](https://restful-booker.herokuapp.com/apidoc/index.html)

---

## 🌐 Core Concepts

### URL (Uniform Resource Locator)
A specific character string that constitutes a reference to a resource. It is the **Address**. It tells the system exactly where the resource is located on the network.

### cURL (Client URL)
A command-line tool and library used for transferring data with URLs. It is the **Action/Transport**. It is the "messenger" that visits the address to perform an operation (GET, POST, DELETE, etc.).

---

## 🛠 HTTP Methods (The Verbs)

### GET: Retrieve Data
* **Purpose:** Returns the IDs or details of entities that exist within the API.
* **Data Handling:** Query parameters are stored directly in the **URL**.
* **Filtering:** Can take optional **Query Strings** (e.g., `?id=123`) to search and return a specific subset of data.
* **Characteristic:** Should be "Idempotent" and "Safe" (should not change the state of the server).

### POST: Create Data
* **Purpose:** Creates a new entity in the API.
* **Data Handling:** Requires a **Request Body** (usually in JSON or XML format).
* **Authentication:** Often used for `Auth - CreateToken` to generate a sensitive token required for restricted actions.

### PUT: Replace Data
* **Purpose:** Updates a current entity by replacing the entire resource.
* **Requirement:** Usually requires the full payload. If you omit a field, it may be overwritten as null.

### PATCH: Partial Update
* **Purpose:** Updates a current entity with a **partial payload**.
* **Efficiency:** Only the fields you send are modified; others remain untouched.

### DELETE: Remove Data
* **Purpose:** Deletes a specific entity from the API.
* **Risk:** High-impact operation; often requires elevated permissions (Token).

---

## 📦 Postman Organization
### Collections
All requests in Postman are organized into **Collections**. These allow for:
* Grouping requests by API or Feature.
* Running automated test suites using the **Collection Runner**.
* Defining variables (Environment/Global) to avoid hardcoding values.

---

[The Restful Booker API for API testing](https://restful-booker.herokuapp.com/apidoc/index.html#api-Booking-DeleteBooking)

## "CRUD Testing"

> Verifying the complete lifecycle of a piece of data
---

### Mapping CRUD to HTTP Verbs

| Letter | Operation | HTTP Verb | Example Action |
|---|---|---|---|
| C | Create | POST | Adding a new entity to the system |
| R | Read | GET | Viewing the details of that entity |
| U | Update | PUT / PATCH | Changing the date or name on the booking |
| D | Delete | DELETE | Removing the booking entirely |
