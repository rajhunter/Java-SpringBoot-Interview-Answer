**✅ Basic Comparison: MySQL vs Oracle**

**1. What is the difference between MySQL and Oracle?**

  ------------------------------------------------------------------------
  **Feature**    **MySQL**                      **Oracle**
  -------------- ------------------------------ --------------------------
  License        Open-source (GPL)              Commercial (Proprietary)

  Cost           Free (with paid editions)      Requires licensing

  Storage        Supports multiple (InnoDB,     Uses tablespaces,
  Engines        MyISAM)                        segments, etc

  ACID           With InnoDB                    Full compliance
  Compliance                                    

  PL/SQL Support Not available                  Fully supports PL/SQL

  Partitioning   Limited                        Advanced

  Replication    Master-slave, group            Advanced (GoldenGate,
                                                Streams)

  Sharding       Manual/Group Replication       Oracle Sharding
  ------------------------------------------------------------------------

**✅ Architecture and Internals**

**2. What are the key components of MySQL architecture?**

- **Client Layer:** Handles connection/threading.

- **SQL Layer:** Query parsing, optimization.

- **Storage Engine Layer:** InnoDB, MyISAM, Memory, etc.

- **Buffer Pool / Caches:** InnoDB buffer pool, key cache.

**3. Describe Oracle DB architecture.**

- **Instance (SGA + Background Processes)**:

  - **SGA** (Shared Global Area): buffer cache, shared pool, redo log
    buffer.

  - **Background Processes**: DBWR, LGWR, SMON, PMON.

- **Database**: Consists of datafiles, control files, redo logs.

**✅ SQL/PLSQL Differences**

**4. Is PL/SQL supported in MySQL?**

No. MySQL uses stored procedures/functions but does **not support full
PL/SQL**. Oracle has advanced exception handling, cursors, packages,
triggers.

**5. Can you run recursive queries in both?**

- **MySQL**: Yes, using **CTE** (from v8.0+).

- **Oracle**: Yes, using **CONNECT BY** and **CTE (WITH RECURSIVE)**.

**✅ Performance Tuning**

**6. How does query optimization differ in MySQL vs Oracle?**

  ------------------------------------------------------------------------
  **Feature**         **MySQL**                  **Oracle**
  ------------------- -------------------------- -------------------------
  Optimizer Hints     Limited                    Extensive (/\*+ USE_NL,
                                                 etc. \*/)

  Execution Plan Tool EXPLAIN, EXPLAIN ANALYZE   EXPLAIN PLAN, AUTOTRACE

  Cost-Based          Yes                        Yes (with optimizer
  Optimization                                   stats)

  Parallel Query      Limited (InnoDB Cluster)   Advanced
  Support                                        
  ------------------------------------------------------------------------

**7. What tools are used for performance tuning?**

- **MySQL**:

  - EXPLAIN, SHOW PROFILE, slow_query_log

  - Percona Toolkit

- **Oracle**:

  - AWR, ADDM, SQL Trace, TKPROF, OEM

**✅ Backup & Recovery**

**8. Backup techniques in MySQL?**

- mysqldump

- mysqlpump

- Binary logs (point-in-time recovery)

- Xtrabackup (Percona)

**9. Backup tools in Oracle?**

- RMAN (Recovery Manager)

- Data Pump (expdp/impdp)

- Flashback technology (table, database)

**✅ High Availability and Replication**

**10. How is replication handled in MySQL vs Oracle?**

  ----------------------------------------------------------------------------
  **Feature**   **MySQL**                         **Oracle**
  ------------- --------------------------------- ----------------------------
  Replication   Native async, group replication   Data Guard, GoldenGate

  Sharding      Manual or MySQL Fabric, InnoDB    Oracle Sharding
                cluster                           

  Clustering    Galera, MySQL Cluster             RAC (Real Application
                                                  Clusters)

  Failover      MySQL Router or ProxySQL          Automatic with Oracle
                                                  Clusterware
  ----------------------------------------------------------------------------

**✅ Security**

**11. Security differences between MySQL and Oracle?**

  -------------------------------------------------------------------------
  **Security       **MySQL**         **Oracle**
  Feature**                          
  ---------------- ----------------- --------------------------------------
  Authentication   Native, PAM, LDAP OS, Kerberos, LDAP, External

  Role-based       Yes (from v8)     Advanced Role + Profile Mgmt
  Access                             

  Auditing         Limited (audit    Advanced (FGA, DBMS_AUDIT, Unified
                   plugin)           Audit)

  Data Masking     Manual            Advanced Security Option (ASO)

  TDE (Encryption) Yes (Enterprise)  Yes (Transparent Data Encryption)
  -------------------------------------------------------------------------

**✅ Cross Questions for Experienced Roles**

**12. How do you perform data migration between MySQL and Oracle?**

- Use **Oracle GoldenGate**, **SQL Developer**, or **Data Integrator
  (ODI)**.

- For MySQL → Oracle:

  - Dump schema/data (CSV/XML), then import.

  - Use ETL tools for transformation.

**✅ Scenario-Based Questions**

**13. How would you optimize a slow MySQL query with joins?**

- Check EXPLAIN output.

- Add missing indexes.

- Avoid SELECT \*.

- Use STRAIGHT_JOIN to force join order.

- Break down complex joins with temporary tables.

**14. A user reports a locking issue in Oracle. How will you debug it?**

- Use:

  - V\$LOCK, V\$SESSION, DBA_BLOCKERS, DBA_WAITERS

  - ALTER SYSTEM KILL SESSION if needed

  - Identify and tune long-running queries

**✅ PL/SQL and Stored Procedure**

**15. How do stored procedures differ in MySQL vs Oracle?**

  -----------------------------------------------------------------------
  **Feature**      **MySQL**                **Oracle**
  ---------------- ------------------------ -----------------------------
  Exception        Limited (DECLARE         Advanced (BEGIN \...
  Handling         CONTINUE)                EXCEPTION)

  Packages         Not Supported            Fully supported

  Cursors          Supported                Supported with advanced
                                            options

  Trigger Timing   BEFORE/AFTER             BEFORE/AFTER/INSTEAD OF
  -----------------------------------------------------------------------


**✅ MySQL vs Oracle: MCQ Quiz**

**1. Which of the following is true about MySQL?**

A. It\'s a proprietary database only\
B. It does not support replication\
C. It\'s open-source with pluggable storage engines\
D. It uses PL/SQL as its procedural language\
👉 **Answer:** C\
📘 **Explanation:** MySQL is open-source and supports various storage
engines like InnoDB, MyISAM.

**2. Oracle uses which language for stored procedures?**

A. T-SQL\
B. PL/SQL\
C. SQL/PSM\
D. MySQL Script\
👉 **Answer:** B

**3. What is the default storage engine for MySQL 8.0+?**

A. MyISAM\
B. InnoDB\
C. MEMORY\
D. Archive\
👉 **Answer:** B

**4. Which Oracle feature allows rolling back to a point in time?**

A. Flashback\
B. Recycle Bin\
C. Redo Log\
D. Archive Log\
👉 **Answer:** A

**5. Which tool is used for backup in Oracle?**

A. mysqldump\
B. Xtrabackup\
C. RMAN\
D. expdp\
👉 **Answer:** C

**6. Which tool can be used for performance tuning in Oracle?**

A. ADDM\
B. EXPLAIN\
C. slow_query_log\
D. Percona Toolkit\
👉 **Answer:** A

**7. Which replication method is native to MySQL?**

A. GoldenGate\
B. Data Guard\
C. MySQL Replication\
D. Streams\
👉 **Answer:** C

**8. What's used to monitor locking issues in Oracle?**

A. SHOW ENGINE STATUS\
B. V\$LOCK\
C. processlist\
D. pg_locks\
👉 **Answer:** B

**9. Which of the following supports full ACID compliance?**

A. MyISAM\
B. MEMORY\
C. InnoDB\
D. CSV\
👉 **Answer:** C

**10. Oracle RAC provides what feature?**

A. In-memory tables\
B. Row-level locks\
C. High Availability via clustering\
D. Parallel backup\
👉 **Answer:** C

**🔄 MySQL vs Oracle Features**

**11. Which MySQL version introduced Common Table Expressions (CTE)?**

A. 5.5\
B. 5.7\
C. 8.0\
D. 8.1\
👉 **Answer:** C

**12. Which storage engine supports full-text indexing in MySQL?**

A. MEMORY\
B. InnoDB (8+)\
C. MyISAM\
D. ARCHIVE\
👉 **Answer:** C

**13. Which optimizer hint syntax is correct in Oracle?**

A. /\*+ USE_INDEX(table column) */\
B. \-- OPTIMIZER USE_INDEX\
C. /*+ INDEX(table index_name) \*/\
D. #+ USE_INDEX\
👉 **Answer:** C

**14. In Oracle, what is the purpose of SGA?**

A. Handles background jobs\
B. Stores control files\
C. Shared memory area for cache and buffers\
D. Manages redo logs\
👉 **Answer:** C

**15. MySQL does not support which feature natively (without plugins)?**

A. Foreign key constraints\
B. Triggers\
C. Transparent Data Encryption\
D. Views\
👉 **Answer:** C

**🧠 Advanced and Scenario-Based**

**16. Which tool supports hot backup in MySQL (InnoDB)?**

A. mysqldump\
B. mysqlpump\
C. Xtrabackup\
D. Oracle RMAN\
👉 **Answer:** C

**17. Which of the following is used for logical backups in Oracle?**

A. RMAN\
B. flashback\
C. expdp/impdp\
D. Data Guard\
👉 **Answer:** C

**18. Which query tool gives the execution plan in MySQL?**

A. tkprof\
B. autotrace\
C. EXPLAIN\
D. V\$SQL_PLAN\
👉 **Answer:** C

**19. In Oracle, which feature ensures data security at rest?**

A. DBMS_CRYPTO\
B. Transparent Data Encryption (TDE)\
C. VPD\
D. Oracle Vault\
👉 **Answer:** B

**20. Which MySQL tool supports group replication?**

A. mysqlshell\
B. mysqldump\
C. mysqladmin\
D. mysqlimport\
👉 **Answer:** A

**🔒 Security & Admin**

**21. Which type of authentication is supported in Oracle?**

A. Native\
B. Kerberos\
C. LDAP\
D. All of the above\
👉 **Answer:** D

**22. In Oracle, what is a tablespace?**

A. A temporary table\
B. A logical storage container for segments\
C. An index\
D. A backup directory\
👉 **Answer:** B

**23. Which tool shows the slowest queries in MySQL?**

A. Oracle Grid Control\
B. EXPLAIN PLAN\
C. slow_query_log\
D. Oracle ADDM\
👉 **Answer:** C

**24. Which data type is NOT supported in Oracle?**

A. BLOB\
B. TEXT\
C. CLOB\
D. RAW\
👉 **Answer:** B\
📘 **Explanation:** TEXT is a MySQL-specific datatype. Oracle uses
CLOB/BLOB.

**25. How do you enforce uniqueness in Oracle tables?**

A. Use INDEX\
B. Use VIEW\
C. Use UNIQUE constraint\
D. Use SEQUENCE\
👉 **Answer:** C

**🔸 Q1. How do you fetch the top 5 highest salaries from an employee
table?**

**MySQL:**

sql

CopyEdit

SELECT \* FROM employee ORDER BY salary DESC LIMIT 5;

**Oracle:**

sql

CopyEdit

SELECT \* FROM (

SELECT \* FROM employee ORDER BY salary DESC

) WHERE ROWNUM \<= 5;

**🔸 Q2. How do you get the second highest salary?**

**MySQL:**

sql

CopyEdit

SELECT MAX(salary) FROM employee

WHERE salary \< (SELECT MAX(salary) FROM employee);

**Oracle (Oracle 12c+):**

sql

CopyEdit

SELECT salary FROM (

SELECT salary, DENSE_RANK() OVER (ORDER BY salary DESC) AS rnk

FROM employee

) WHERE rnk = 2;

**🔸 Q3. Query to list employee count by department where count \> 5**

**MySQL & Oracle:**

sql

CopyEdit

SELECT dept_id, COUNT(\*) AS emp_count

FROM employee

GROUP BY dept_id

HAVING COUNT(\*) \> 5;

**🔸 Q4. What's the syntax for a LEFT JOIN?**

**MySQL & Oracle:**

sql

CopyEdit

SELECT e.name, d.name

FROM employee e

LEFT JOIN department d ON e.dept_id = d.id;

**🔸 Q5. Create a view to show active employees**

**MySQL:**

sql

CopyEdit

CREATE VIEW active_employees AS

SELECT \* FROM employee WHERE status = \'ACTIVE\';

**Oracle:**

sql

CopyEdit

CREATE OR REPLACE VIEW active_employees AS

SELECT \* FROM employee WHERE status = \'ACTIVE\';

**🔸 Q6. How to get table metadata?**

**MySQL:**

sql

CopyEdit

DESCRIBE employee;

\-- or

SHOW COLUMNS FROM employee;

**Oracle:**

sql

CopyEdit

DESC employee;

\-- or

SELECT column_name, data_type FROM user_tab_columns WHERE table_name =
\'EMPLOYEE\';

**🔸 Q7. How do you add a column to a table?**

**MySQL & Oracle:**

sql

CopyEdit

ALTER TABLE employee ADD email VARCHAR(100);

**🔸 Q8. How to get current date/time?**

**MySQL:**

sql

CopyEdit

SELECT NOW(); \-- Current date and time

**Oracle:**

sql

CopyEdit

SELECT SYSDATE FROM dual;

**🔸 Q9. How to write a stored procedure that returns total employee
count?**

**MySQL:**

sql

CopyEdit

DELIMITER //

CREATE PROCEDURE get_employee_count()

BEGIN

SELECT COUNT(\*) AS total FROM employee;

END;

//

DELIMITER ;

**Oracle:**

sql

CopyEdit

CREATE OR REPLACE PROCEDURE get_employee_count(p_count OUT NUMBER)

AS

BEGIN

SELECT COUNT(\*) INTO p_count FROM employee;

END;

**🔸 Q10. How to paginate results (10 rows per page)?**

**MySQL (LIMIT OFFSET):**

sql

CopyEdit

SELECT \* FROM employee LIMIT 10 OFFSET 20; \-- Page 3

**Oracle (12c+ FETCH FIRST):**

sql

CopyEdit

SELECT \* FROM employee

OFFSET 20 ROWS FETCH NEXT 10 ROWS ONLY;

**🧠 Bonus: System & Admin Queries**

**🔹 Check current database version**

**MySQL:**

sql

CopyEdit

SELECT VERSION();

**Oracle:**

sql

CopyEdit

SELECT \* FROM v\$version;

**🔹 Check slow queries (MySQL)**

sql

CopyEdit

SHOW VARIABLES LIKE \'slow_query_log%\';

SHOW FULL PROCESSLIST;

**🔹 Find blocking session in Oracle**

sql

CopyEdit

SELECT blocking_session, sid, serial# FROM v\$session WHERE
blocking_session IS NOT NULL;

**🔹 Get tablespace usage (Oracle)**

sql

CopyEdit

SELECT tablespace_name, used_space, tablespace_size

FROM dba_tablespace_usage_metrics;
