# update-in-jdbc

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

public class updatedata {
    public static void main(String[] args) {
    	//System.out.println("hello");
        // Create a variable for the connection string.
        String connectionUrl = "jdbc:sqlserver://OPTIMUS-75:1433;databaseName=train;user=sa;password=root";

        try (Connection con = DriverManager.getConnection(connectionUrl);
        	Statement stmt = con.createStatement();) {
            String SQL = "UPDATE traindetails SET trainname = 'fast' WHERE trainid= 1025";
            ResultSet rs = stmt.executeQuery(SQL);
        	
            // Iterate through the data in the result set and display it.
            while (rs.next()) {
                System.out.println(rs.getString("trainname"));
            }
        }
        // Handle any errors that may have occurred.
        catch (SQLException e) {
            e.printStackTrace();
        }
    }
}





