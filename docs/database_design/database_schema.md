# Database Schema 
- Student
  + Student_id
  +  Name
  +  Email
  + Class
- Teacher
  + Teacher_id
  + Name
  + Email
  + Class
- Admin
  + Admin_id
  + Name
  + Email
- Class
  + Class_id
  + Class_name
  + Teacher
- Practice
  + Practice_id
  + Student_id
  + Teacher_id
  + Conversation
  + ChatGPT_feedback
  + Teacher_feedback

## Database Tables 


### Student Table

| Attribute  | Type    | Key         |
|------------|---------|-------------|
| Student_id | Integer | Primary Key |
| Name       | String  |             |
| Email      | String  |             |
| Class_id   | Integer | Foreign Key |

Note: Each student can only be in one class.

#### Example Student Table

| Student_id | Name       | Email                | Class_id |
|------------|------------|----------------------|----------|
| 1          | "John Doe" | "john_doe@email.com" | 1        |



### Teacher Table

| Attribute  | Type    | Key         |
|------------|---------|-------------|
| Teacher_id | Integer | Primary Key |
| Name       | String  |             |
| Email      | String  |             |


#### Example Teacher Table

| Teacher_id | Name       | Email                | 
|------------|------------|----------------------|
| 1          | "Jane Doe" | "jane_doe@email.com" |




### Admin Table

| Attribute | Type    | Key         |
|-----------|---------|-------------|
| Admin_id  | Integer | Primary Key |
| Name      | String  |             |
| Email     | String  |             |

#### Example Admin Table

| Admin_id | Name    | Email             |
|----------|---------|-------------------|
| 1        | "Admin" | "admin@email.com" |


### Class Table

| Attribute  | Type    | Key         |
|------------|---------|-------------|
| Class_id   | Integer | Primary Key |
| Class_name | String  |             |
| Teacher_id | Integer | Foreign Key |


### Example Class Table

| Class_id | Class_name     | Teacher_id |
|----------|----------------|------------|
| 1        | "Radiology"    | 1          |
| 2        | "Neuroanatomy" | 2          |


### Student_Class Table

| Attribute  | Type    | Key         |
|------------|---------|-------------|
| Student_id | Integer | Foreign Key |
| Class_id   | Integer | Foreign Key |

Note: Each student can only be in one class. But each class can have 1 to many students.

#### Example Student_Class Table

| Student_id | Class_id |
|------------|----------|
| 1          | 1        |



### Practice Table 

| Attribute        | Type    | Key         |
|------------------|---------|-------------|
| Practice_id      | Integer | Primary Key |
| Student_id       | Integer | Foreign Key |
| Teacher_id       | Integer | Foreign Key |
| Date             | String  |             |
| Conversation     | String  |             |
| ChatGPT_feedback | String  |             |
| Teacher_feedback | String  |             |

#### Example Practice Table

| Practice_id | Student_id | Teacher_id | Date         | Conversation             | ChatGPT_feedback                                                                                                                    | Teacher_feedback                        |
|-------------|------------|------------|--------------|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------|
| 1           | 1          | 1          | "10/03/2023" | "Full-conversation text" | "You first attempt at delivering bad news went well! One thing you will want to work on is being more authoritative in your speech" | "This was an excellent first practice!" |

