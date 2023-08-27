# PostGres-Golang-Integration
In this project, we will integrate postgres with Golang


Important Postgres Commands:-

1. Listing all the database:- \l
2. Create database:- CREATE DATABSE newdb
3. Connecting to a database:- \c newdb
4. Switching back to postgres db:- \c postgres
5. listing all the table in the database:- \d
6. describing table in the table for its schema:- \d newtable
7. Create table:- CREATE TABLE newtable
8. Drop table:- DROP TABLE newtable
9. Enable Expand on:- \x
    
# PostGres-Golang-Integration

# 1. Import the following packages:-		
   a. database/sql is the package for establishing connection with the database
   b. github.com/lib/pq is the driver
   
           import (
        	    "database/sql"
        	    _ "github.com/lib/pq"
            )
   
# 2. Connecting with postgres DB
		// In the main func,the below peice of code would help us to connect the our golang repo with the postgres databse
		          const (
		            	host     = "localhost"
		            	port     = 5432
		            	user     = "postgres"
		            	password = "admin"
		            	dbname   = "shoppingdb"
		            )
                                psqlconn := fmt.Sprintf("host=%s port=%d user=%s password=%s dbname=%s sslmode=disable", host, port, user, password, dbname)
                                db, err = sql.Open("postgres", psqlconn)
                                if err != nil {
                                        log.Printf("Error %s when opening DB\n", err)
                                        return
                                }
# 3. Check if the connection has been established
		// once the connection has been established, we can check if the connection is successful by pinging the database:-
           	        err = db.Ping()
                        if err != nil {
                               log.Printf("Error %s when pinging DB\n", err)
                               return
                        }
# 4. Querying database:-
                
