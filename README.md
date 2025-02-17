# 🚀 Hibernate One-to-One Relationship Example

This repository contains a **Hibernate One-to-One Relationship** implementation using Java and JPA annotations. The project demonstrates how to map a **one-to-one relationship** in Hibernate using different approaches.

## ✨ Features
- 🔗 One-to-One mapping with `@OneToOne` and `@JoinColumn` (Foreign Key approach)
- 🔄 Bidirectional One-to-One mapping with `mappedBy`
- 🔑 Primary Key-based One-to-One mapping with `@PrimaryKeyJoinColumn`
- 🛠 Uses **Hibernate ORM** with **MySQL/Jakarta Persistence API**
- 📌 Uses **Lombok** for reducing boilerplate code
- 📚 Simple and clear examples for easy understanding

## 🛠 Technologies Used
- ☕ **Java 11+**
- 🏗 **Hibernate ORM**
- 📦 **Jakarta Persistence API (JPA)**
- 🗄 **MySQL**
- ✍️ **Lombok**
- 💻 **IntelliJ IDEA / VS Code**

## 📖 Concept Explanation
### 🔍 **What is a One-to-One Relationship?**
A **One-to-One** relationship in Hibernate is a database association where a record in one table is associated with exactly one record in another table. This is commonly used when an entity has a related entity that is unique to it.

### 📌 **Types of One-to-One Mappings in Hibernate**
1. 🔗 **Foreign Key Mapping:** Uses a foreign key in one table to reference the primary key of another table.
2. 🔄 **Bidirectional Mapping:** Both entities maintain a reference to each other.
3. 🔑 **Primary Key Mapping:** The primary key of one table is also used as the foreign key of another table.

### 🤔 **Why Use One-to-One Mapping?**
- ✅ Ensures **data consistency** by avoiding duplicate data.
- 📊 Helps **normalize** the database structure.
- ⚡ Improves **query performance** by reducing redundancy.

### 📌 **Example Use Case**
Consider an **Employee** who has a unique **Address**. Instead of storing all address fields in the Employee table, we store them separately in the Address table and establish a **one-to-one** relationship.

## 🏃‍♂️ How to Run
1. 📥 **Clone the repository**
   ```sh
   git clone https://github.com/Matheesha-Abiman/hibernate-one-to-one-example.git
   cd hibernate-one-to-one-example
   ```
2. ⚙️ **Configure Database** (In `hibernate.cfg.xml`)
3. 🚀 **Build and Run**
   ```sh
   javac -cp ".:lib/*" com/example/MainApplication.java
   java -cp ".:lib/*" com.example.MainApplication
   ```

## 📝 Example Code
### 🏗 **1. Entity Classes**
#### 👨‍💼 **Employee.java**
```java
@Entity
@Data
public class Employee {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
    
    @OneToOne
    @JoinColumn(name = "address_id")
    private Address address;
}
```

#### 🏡 **Address.java**
```java
@Entity
@Data
public class Address {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String city;
    private String country;
}
```

## 🤝 Contributing
Feel free to fork this repository and submit pull requests with improvements! 🎯
