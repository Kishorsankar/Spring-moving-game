FarmPortal
│
├── index.html        (Frontend)
├── style.css         (Frontend)
├── LoginServlet.java (Backend)
└── web.xml

<!DOCTYPE html>
<html>
<head>
<title>Farm Management Portal</title>
<link rel="stylesheet" href="style.css">
</head>

<body>

<h2>Farm Management Login</h2>

<form action="login" method="post">

<label>Username:</label>
<input type="text" name="username" required>

<label>Password:</label>
<input type="password" name="password" required>

<button type="submit">Login</button>

</form>

</body>
</html>
import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;

public class LoginServlet extends HttpServlet {

    protected void doPost(HttpServletRequest request,
                          HttpServletResponse response)
                          throws ServletException, IOException {

        String username = request.getParameter("username");
        String password = request.getParameter("password");

        PrintWriter out = response.getWriter();

        if(username.equals("admin") && password.equals("1234"))
        {
            out.println("<h2>Login Successful</h2>");
        }
        else
        {
            out.println("<h2>Login Failed</h2>");
        }
    }
}

<web-app>

<servlet>
<servlet-name>LoginServlet</servlet-name>
<servlet-class>LoginServlet</servlet-class>
</servlet>

<servlet-mapping>
<servlet-name>LoginServlet</servlet-name>
<url-pattern>/login</url-pattern>
</servlet-mapping>

</web-app>
