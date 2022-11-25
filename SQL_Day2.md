import java.sql.*;
 import java.util.*;

public class MainClass {
    static final String DB_url="jdbc:mysql://localhost:3306/cognidemo";
    static final String user="root";
    static final String pass="pass@word1";
   static final String Query="Select * from customer";
    public static void main(String[] args)
    {try {
        Connection conn = DriverManager.getConnection(DB_url, user, pass);
        Statement st=conn.createStatement();
        String query="Drop table customer";
        st.executeUpdate(query);
       String createQuery="create table customer (Customer_Id INT , Customer_Name varchar(255),Customer_Age INT, Customer_City varchar(255),PRIMARY KEY(Customer_Id))";
       st.executeUpdate(createQuery);
       String insertQuery="insert into customer values(1,'Amit',27,'Hyderabad')";
        st.executeUpdate(insertQuery);
        insertQuery=   "insert into customer values(2,'Abhay',27,'Mumbai')";
        st.executeUpdate(insertQuery);
            insertQuery = "insert into customer values(3,'Bhuvan',23,'Delhi')";
        st.executeUpdate(insertQuery);
            insertQuery = "insert into customer values(4,'Chaithu',20,'Pune')";
        st.executeUpdate(insertQuery);
             insertQuery  = "insert into customer values(5,'Suresh',34,'Bangalore')";
        st.executeUpdate(insertQuery);
             insertQuery = "insert into customer values(6,'Ramesh',46,'Hyderabad')";
        st.executeUpdate(insertQuery);
       // Query="Select * from customer";
        String updateQuery="update customer set customer.Customer_Age=38 where customer.Customer_Id=3";
        st.executeUpdate(updateQuery);
        String deleteQuery="delete from customer where customer.Customer_Age<30";
        st.executeUpdate(deleteQuery);
        ResultSet rs=st.executeQuery(Query);
        System.out.println("Id "+" : "+"Name"+" : "+"Age"+" : "+"City");
        while(rs.next())
        {
           // System.out.println(rs.getInt("Customer_Id")+" "+ rs.getString("Customer_Name")+" "+rs.getInt("Customer_Age")+ " "+rs.getString("Customer_City"));
            System.out.println(rs.getInt("customer.Customer_Id")+" : "+ rs.getString("customer.Customer_Name")+" : "+rs.getInt("customer.Customer_Age")+" : "+rs.getString("customer.Customer_City"));
        }
    }
    catch(Exception e)
    {
        System.out.println(e);
    }

       
    }
}
