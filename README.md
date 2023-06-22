## Ex-25 Create a job portal application using react,SpringBoot,SQL
## Aim:
To create an job portal application using SpringBoot and SQL.

## Algorithm:
### Step 1:-
Open Spring Initialzr.

### Step 2:-
Save the zip file.

### Step 3:-
Open an IDE like IntelliJ,Oracle etc.

### Step 4:-
Open the folder in the IDE.

### Step 5:-
Create Components.

### Step 6:-
Connect the database with the SpringBoot.

## Program:

JobPortal.java
```java
package com.Jobportal.jobportal.job;

import jakarta.persistence.*;
import org.junit.platform.commons.annotation.Testable;
import org.springframework.boot.autoconfigure.domain.EntityScan;

import java.time.LocalDate;
import java.time.Period;

@Entity
@Table
public class Jobportal {
    @Id
    @SequenceGenerator(
            name = "jobportal_sequence",
            sequenceName = "jobportal_sequence",
            allocationSize = 1
    )
    @GeneratedValue(
            strategy = GenerationType.SEQUENCE,
            generator = "jobportal_sequence"
    )
    private Long jobportalId;
    private String jobportalName;
    @Transient
    private Integer jobportalAge;
    private LocalDate jobportalDob;
    private String jobportalEmail;

    public jobportal() {
    }

    public jobportal(Long jobportalId, String jobportalName, LocalDate jobportalDob, String jobportalEmail) {
        this.jobportalId = jobportalId;
        this.jobportalName =jobportalName;
        this.jobportalDob = jobportalDob;
        this.jobportalEmail =jobportalEmail;
    }

    public Long getjobportalId() {
        return jobportalId;
    }

    public void setjobportalId(Long jobportalId) {
        jobportalId = jobportalId;
    }

    public String getjobportalName() {
        return jobportalName;
    }

    public void setjobportalName(String jobportalName) {
        jobportalName = jobportalName;
    }

    public Integer getjobportalAge() {
        return Period.between(jobportalDob,LocalDate.now()).getYears();
    }

    public void setjobportalAge(Integer jobportalAge) {
        jobportalAge = jobportalAge;
    }

    public LocalDate getjobportalDob() {
        return jobportalDob;
    }

    public void setjobportalDob(LocalDate jobportalDob) {
        jobportalDob = jobportalDob;
    }

    public String getjobportalEmail() {
        return jobportalEmail;
    }

    public void setjobportalEmail(String jobportalEmail) {
        jobportalEmail = jobportalEmail;
    }

    @Override
    public String toString() {
        return "Jobportal{" +
                "jobportalId=" + jobportalId +
                ", jobportalName='" + jobportalName + '\'' +
                ", jobportalAge=" + jobportalAge +
                ", jobportalDob=" + jobportalDob +
                ", jobportalEmail='" + jobportalEmail + '\'' +
                '}';
    }
}
```
applications.properties
```java
spring.datasource.url=jdbc:postgresql://localhost:5432/hosman_db
spring.datasource.username=postgres
spring.datasource.password=saiabi@123
spring.jpa.hibernate.ddl-auto=create-drop
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
spring.jpa.properties.hibernate.format_sql=true
```
App.js
```java
import React from "react"
import './App.css';
import { BrowserRouter as Router, Route, Routes, Link } from "react-router-dom";
import jobportalComponent from './components/jobportalComponent/jobportalComponent';
import HeaderComponent from "./components/HeaderComponent/HeaderComponent";
import jobportalComponent from "./components/jobportalComponent/jobportalComponent";
import jobportalComponent from "./components/jobportalComponent/jobportalnComponent";

function App() {
  return (
    <Router>
            <div className="container">
              <HeaderComponent/>
              
            <nav className="nav-menu">
                <Link to="/" >Home</Link>
                <Link to="/admin/add" >Add Member</Link>
                <Link to="/admin/delete" >Delete Member</Link>
            </nav>
           <Routes>
                 <Route exact path='/' element={<jobportalComponent/>}></Route>
                 <Route path='/admin/add' element={<jobportalComponent/>}></Route>
                 <Route path='/admin/delete' element={<jobportalComponent/>}></Route>
          </Routes>
          </div>
       </Router>
  );
}

export default App;
```
## Output:
![jobportal](https://github.com/SarankumarJ/Job-Portal-Application/assets/94778101/5a3d6c8f-8c8c-416f-b432-5f4172c033eb)


## Result:
Thus we have successfully created an job portal application using SpringBoot and SQL.
