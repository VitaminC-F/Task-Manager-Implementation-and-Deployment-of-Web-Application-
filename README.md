1. Database Setup:
   - Create a database with the name defined in your settings.py.
   - For example, if your database name is "mytasksdb," make sure it matches the name in your settings.

2. Run the Query:
   - Execute the following SQL query to create the necessary table:
     sql
     CREATE TABLE tasks (
         id INT AUTO_INCREMENT PRIMARY KEY,
         user_id INT NOT NULL,
         title VARCHAR(100) NOT NULL,
         description TEXT,
         status ENUM('pending', 'in_progress', 'completed') DEFAULT 'pending',
         due_date DATE,
         created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
         updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
     );
     

3. Update Database Details:
   - Replace the host, username, password, and port in your settings.py file with the details of your newly created database.

4. Configure Allowed Hosts:
   - In your settings.py, find the ALLOWED_HOSTS setting and add 127.0.0.1 (localhost) to the list.

5. Run Migrations:
   - Execute the following command to apply migrations:
     
     python manage.py migrate
     

6. Start the Server:
   - Finally, run the development server with:
     
     python manage.py runserver
