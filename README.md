# mscams
A web-based application management system for Middlebury student council to manage their funding applications


### Tech Stack and Focus
- Stacks: Node.js, react.js
- Database: Postgres or MongoDB
- Focus: Equally focused full-stack app

### Goals:
- Streamline the management workflow of Student Council funding applications, reducing wait time for students as well as administrative time for council members

### Users:
- Admins: Student Council budgetary committee members
- Students: Middlebury students who need to apply for funding from student council
- Clubs (accounts operated by students): Clubs who need to check club balance and apply for funding

### Data: 
- Eventually, data from Middlebury Student Services will be used for club and student info. During development, I will use mock data to create a prototype.

### Approach:
1. Backend:
    - Database Schema: 
      - Users: Need email, and password, and name to sign up. There are three types of user accounts: admin, student and club. Each type with required different additional signup information
      - Applications: Need applicant, amount and type. Different types of application will correspond to different required fields. 
      - Votes: Boolean value with two foreign keys - voter and application being voted on. Admins can vote on an application. 
    - Routes:
      - Auth: Can only register as students or clubs with university email (admin accounts will be set up in the database for now)
      - Applications: Get all requires admin priviledge, get by id require correct user. PATCH request requires correct user
      - Users: Required correct user or admin priviledge
