# 🏏 AIUB Cricket Team Management System

**Course:** Introduction to Database 
**Supervisor:** MD Sajid Bin Faisal  
**Student:** Bijoy Ahamed (22-449373-3)

---

## 📌 Overview
Database system for AIUB Cricket Team to manage players, selectors, officials, coaches, events, and tournaments.

**Tools:** Oracle 10g, draw.io, Java JDBC, XAMPP/MySQL

---

## 📊 Tables (14)

| Table | PK | FK |
|-------|----|----|
| Player | P_ID | - |
| Selector | S_ID | - |
| Confirm | P_ID | S_ID |
| Address | City,Country | - |
| Official | O_ID | - |
| Selects | P_ID | O_ID |
| Detail_Address | Zone,Area,City,Country | - |
| Coache | C_ID | - |
| Guid | P_ID | C_ID |
| Appoint | O_ID | C_ID |
| Detail | Zone,Area | - |
| Event | E_ID | - |
| Moderator | O_ID | E_ID |
| Operates | T_No | E_ID |

**Normalization:** UNF → 1NF → 2NF → 3NF

---

## 💻 SQL

```sql
CREATE TABLE Player (
    P_ID NUMBER(6) PRIMARY KEY,
    P_Name VARCHAR2(25),
    P_Position VARCHAR2(20),
    P_Age NUMBER(3),
    Skill VARCHAR2(20),
    Role VARCHAR2(20),
    City VARCHAR2(20)
);

INSERT INTO Player VALUES (49373, 'Bijoy Ahamed', 'Batsman', 23, 'Right-Handed', 'Captain', 'Brahmanbaria');

SELECT * FROM Player WHERE P_Name = 'Bijoy Ahamed';
SELECT COUNT(C_ID) FROM Coache;

🔌 Java Connection
java
Class.forName("com.mysql.jdbc.Driver");
Connection con = DriverManager.getConnection("jdbc:mysql://localhost:3306/aiub_cricket", "root", "");
Statement stmt = con.createStatement();
ResultSet rs = stmt.executeQuery("SELECT * FROM Player");
while(rs.next()) {
    System.out.println(rs.getString("P_Name"));
}
con.close();

🚀 Run
Install XAMPP → Start Apache & MySQL
Create database: aiub_cricket
Run SQL scripts
Add MySQL Connector JAR
Run Java program

✅ Conclusion
Complete database system with 3NF normalization, SQL queries, views, joins, subqueries, and Java connectivity.
