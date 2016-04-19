
#JavaServer Faces (JSF)
###**Why**
JavaServer Faces (JSF) is a MVC web framework that simplifies the construction of user interfaces (UI) for server-based applications by using reusable UI components in a page.JSF provides facility to connect UI widgets with data sources and to server-side event handlers. The JSF specification defines a set of standard UI components and provides an Application Programming Interface (API) for developing components.JSF enables the reuse and extension of the existing standard UI components.

__Benefits__
JSF reduces the effort in creating and maintaining applications which will run on a Java application server and will render application UI on to a target client.JSF facilitates Web application development by
providing reusable UI components

- making easy data transfer between UI components
- managing UI state across multiple server requests
- enabling implementation of custom components
- wiring client side event to server side application code

###**Binding to Managed Beans**
Managed beans work as Model for UI component. They can be easily registered using annotations. This approach keeps beans and there registration at one place and it becomes easier to manage.

__To access in xhtml:__
> "#{beanName.property}"

__Some more examples:__

###**Event Handling**
When a user clicks a JSF button or link or changes any value in text field, JSF UI component fires event which will be handled by the the application code.

When a UI component checks that a user event has happened, it creates an instance of the corresponding event class and adds it to an event list. Then, Component fires the event, i.e., checks the list of listeners for that event and call the event notification method on each listener or handler.

__valueChangeListener__
Value change events get fired when user make changes in input components.

__actionListener__
Action events get fired when user clicks on a button or link component.

__Application Events__
Events firing during JSF lifecycle: PostConstructApplicationEvent, PreDestroyApplicationEvent , PreRenderViewEvent.

> Code here

### **Web application scopes**
__@Request Scope:__ Bean lives as long as the HTTP request-response lives. It get created upon a HTTP request and get destroyed when the HTTP response associated with the HTTP request is finished.

__@Session Scope:__ lives as long as the HTTP session lives. It get created upon the first HTTP request involving this bean in the session and get destroyed when the HTTP session is invalidated.

__@Application Scope:__ Bean lives as long as the web application lives. It get created upon the first HTTP request involving this bean in the application (or when the web application starts up and the eager=true attribute is set in @ManagedBean) and get destroyed when the web application shuts down.
 
__@View Scope:__ lives as long as user is interacting with the same JSF view in the browser window/tab. It get created upon a HTTP request and get destroyed once user postback to a different view.

###**Page Navigation**
Navigation rules are those rules provided by JSF Framework which describe which view is to be shown when a button or link is clicked. 

- Navigation rules can be defined in JSF configuration file named faces-config.xml. 
- They can be defined in managed beans. 
- Navigation rules can contain conditions based on which resulted view can be shown.
- JSF 2.0 provides implicit navigation as well in which there is no need to define navigation rules as such.

JSF 2.0 provides auto view page resolver mechanism named implicit navigation.In this case you only need to put view name in action attribute and JSF will search the correct view page automatically in the deployed application.

####__Auto navigation in JSF page__
Set view name in action attribute of any JSF UI Component.

```xml
<h:form>
   <h3>Using JSF outcome</h3>
   <h:commandButton action="page2" value="Page2" />
</h:form>
```
Here when Page2 button is clicked, JSF will resolve the view name, page2 as page2.xhtml extension, and find the corresponding view file page2.xhtml in the current directory.

####__Auto navigation in Managed Bean__
Define a method in managed bean to return a view name.
```java
@ManagedBean(name = "navigationController", eager = true)
@RequestScoped
public class NavigationController implements Serializable {
   public String moveToPage1(){
      return "page1";
   }
}
```

Get view name in action attribute of any JSF UI Component using managed bean.

```xml
<h:form>
   <h3>Using Managed Bean</h3>
   <h:commandButton action="#{navigationController.moveToPage1}"
   value="Page1" />
</h:form>
```

###**Templating** 
int template, to create space do
```xml
 <ui:insert name="title">Howto Samples</ui:insert>
```

in page, link to the template with 
```xml
<ui:composition template="/template.xhtml">
	...next part here
</ui:composition>
```

define/fill the content/template with
```xml
<ui:define name="title"> Ajax Samples</ui:define>
``` 

**index.xhtml**
```xml
<?xml version='1.0' encoding='UTF-8' ?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml"
      xmlns:ui="http://java.sun.com/jsf/facelets"
      xmlns:f="http://java.sun.com/jsf/core"
      xmlns:h="http://java.sun.com/jsf/html">
    <h:head>
        <title>Facelet Title</title>
    </h:head>
    <h:body>
        <!-- this is a piece of the content im composing and i want to use this template -->
        <ui:composition template="/template.xhtml">
            <!-- define the content that is inserted into a template w/ matching ui:insert-->
            <ui:define name="title">
                Ajax Samples
            </ui:define>
            <ui:define name="body">
                <div>#{AjaxBean.time}</div>
            </ui:define>
        </ui:composition>
    </h:body>
</html>
```

**template.xhtml**
```xml
<?xml version='1.0' encoding='UTF-8' ?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml"
      xmlns:ui="http://java.sun.com/jsf/facelets"
      xmlns:h="http://java.sun.com/jsf/html">
    <h:head>
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
        <title>Facelets - Template Example</title>
        <h:outputStylesheet library="css" name="default.css"/>
    </h:head>
    <body>
        <h1>
            <ui:insert name="title">Howto Samples</ui:insert>
        </h1>
        <h:link outcome="index" value="Back to Home Page"/>
        <p>
            <ui:insert name="body">Welcome</ui:insert>
        </p>
    </body>
</html>
```

###**Using JavaScript in JSF**

###**JSF 2.x AJAX support**
```xml
<!-- Ajax Asg 3 -->
User ID: <h:inputText id="userID" value="#{profileController.theModel.userID}" required="true">
    <f:ajax 
        execute="userID" 
        render="idMessage" 
        event="keyup" 
        listener="#{profileController.checkID()}"
        />
</h:inputText> 
<h:outputText 
    id="idMessage"
    value="#{profileController.idMessage !=null ? profileController.idMessage : ''}"
/>
```

###**Page Forwarding vs. Page Redirection**
**Forward vs Redirect:** JSF by default performs a server page forward while navigating to another page and the URL of the application do not changes.

To enable the page redirection, append faces-redirect=true at the end of the view name.
```xml
<h:form>
   <h3>Forward</h3>
   <h:commandButton action="page1" value="Page1" />
   <h3>Redirect</h3>
   <h:commandButton action="page1?faces-redirect=true" value="Page1" />
</h:form>
```

###**JavaMail**
To send a email with an inline image, the steps followed are:

- Get a Session
- Create a default MimeMessage object and set From, To, Subject in the message.
- Create a MimeMultipart object.
- In our example we will have an HTML part and an Image in the email. So first create the HTML content and set it in the multipart object as:
```java
// first part (the html)
BodyPart messageBodyPart = new MimeBodyPart();
String htmlText = "<H1>Hello</H1><img src=\"cid:image\">";
messageBodyPart.setContent(htmlText, "text/html");
// add it
multipart.addBodyPart(messageBodyPart);
Next add the image by creating a Datahandler as follows:
// second part (the image)
messageBodyPart = new MimeBodyPart();
DataSource fds = new FileDataSource(
 "/home/manisha/javamail-mini-logo.png");
messageBodyPart.setDataHandler(new DataHandler(fds));
messageBodyPart.setHeader("Content-ID", "<image>");
Next set the multipart in the message as follows:
message.setContent(multipart);
```
- Send the message using the Transport object.

####**Full Code Example**
```java
package com.tutorialspoint;

import java.util.Properties;
import javax.activation.DataHandler;
import javax.activation.DataSource;
import javax.activation.FileDataSource;
import javax.mail.BodyPart;
import javax.mail.Message;
import javax.mail.MessagingException;
import javax.mail.PasswordAuthentication;
import javax.mail.Session;
import javax.mail.Transport;
import javax.mail.internet.InternetAddress;
import javax.mail.internet.MimeBodyPart;
import javax.mail.internet.MimeMessage;
import javax.mail.internet.MimeMultipart;

public class SendInlineImagesInEmail {
   public static void main(String[] args) {
      // Recipient's email ID needs to be mentioned.
      String to = "destinationemail@gmail.com";

      // Sender's email ID needs to be mentioned
      String from = "fromemail@gmail.com";
      final String username = "manishaspatil";//change accordingly
      final String password = "******";//change accordingly

      // Assuming you are sending email through relay.jangosmtp.net
      String host = "relay.jangosmtp.net";

      Properties props = new Properties();
      props.put("mail.smtp.auth", "true");
      props.put("mail.smtp.starttls.enable", "true");
      props.put("mail.smtp.host", host);
      props.put("mail.smtp.port", "25");

      Session session = Session.getInstance(props,
         new javax.mail.Authenticator() {
            protected PasswordAuthentication getPasswordAuthentication() {
               return new PasswordAuthentication(username, password);
            }
         });

      try {

         // Create a default MimeMessage object.
         Message message = new MimeMessage(session);

         // Set From: header field of the header.
         message.setFrom(new InternetAddress(from));

         // Set To: header field of the header.
         message.setRecipients(Message.RecipientType.TO,
            InternetAddress.parse(to));

         // Set Subject: header field
         message.setSubject("Testing Subject");

         // This mail has 2 part, the BODY and the embedded image
         MimeMultipart multipart = new MimeMultipart("related");

         // first part (the html)
         BodyPart messageBodyPart = new MimeBodyPart();
         String htmlText = "<H1>Hello</H1><img src=\"cid:image\">";
         messageBodyPart.setContent(htmlText, "text/html");
         // add it
         multipart.addBodyPart(messageBodyPart);

         // second part (the image)
         messageBodyPart = new MimeBodyPart();
         DataSource fds = new FileDataSource(
            "/home/manisha/javamail-mini-logo.png");

         messageBodyPart.setDataHandler(new DataHandler(fds));
         messageBodyPart.setHeader("Content-ID", "<image>");

         // add image to the multipart
         multipart.addBodyPart(messageBodyPart);

         // put everything together
         message.setContent(multipart);
         // Send message
         Transport.send(message);

         System.out.println("Sent message successfully....");

      } catch (MessagingException e) {
         throw new RuntimeException(e);
      }
   }
}
```
###**GET parameters** 

###**Prerendering a page**

----------


#JDBC, Data Sources
###**loading driver**
```java
try {
	Class.forName("org.apache.derby.jdbc.ClientDriver");	
} catch (ClassNotFoundException e) {
    System.err.println(e.getMessage());
    System.exit(0);
}
...
```

###**getting a connection** 
```java
...

try {
	String myDB = "jdbc:derby://localhost:1527/profile2";
	Connection DBConn = DriverManager.getConnection(myDB, "itkstu", "student");

	...

}
...
```

###**preparing SQL statements**
```java
...
String insertString;
Statement stmt = DBConn.createStatement();
insertString = "INSERT INTO reservations VALUES (default, '"+rb.getStore()
        + "', '"+rb.getName()
        + "', '"+rb.getDate()
        + "', "+rb.getNumGuest()
        + ", '" +rb.getTime()
        + "')";
...
```

###**running the query/update**
```java
int rowCount = stmt.executeUpdate(insertString);
// or
ResultSet rs = stmt.executeQuery(query); // will be on next test
```

###**getting the results**
```java
...
// Go through all the result sets items (rows)
while (rs.next()) {
	deptNo = rs.getInt("dept_no");
	name = rs.getString("name");
	empNo = rs.getInt("emp_no");
	salary = rs.getDouble("salary");
	hireDate = rs.getDate("hire_date");

	...
}
```


### Dont forget to end with all this
```java
...
    rs.close();
    stmt.close();
} catch (Exception e) {
    System.err.println("ERROR: Problems with SQL select");
    e.printStackTrace();
}
try {
    DBConn.close();
} catch (SQLException e) {
    System.err.println(e.getMessage());
}
```

###**Using a data source to access and commit changes to a database**
**Create**
```java
@Override
    public int createProfile(ProfileBean aProfile) {
        try {
            Class.forName("org.apache.derby.jdbc.ClientDriver");
        } catch (ClassNotFoundException e) {
            System.err.println(e.getMessage());
            System.exit(0);
        }

        int rowCount = 0;
        
        if(!userExists(aProfile.getUserID()))
        {
            try {
                String myDB = "jdbc:derby://localhost:1527/Project353";
                Connection DBConn = DriverManager.getConnection(myDB, "itkstu", "student");

                String insertString;
                String insertStringLogin;
                
                Statement stmt = DBConn.createStatement();
                insertString = "INSERT INTO Project353.Users_lab3 VALUES ('"
                        + aProfile.getFirstName()
                        + "','" + aProfile.getLastName()
                        + "','" + aProfile.getUserID()
                        + "','" + aProfile.getPassword()
                        + "','" + aProfile.getEmail()
                        + "','" + aProfile.getsecQuestion()
                        + "','" + aProfile.getsecAnswer()
                        + "')";
                
                insertStringLogin = "INSERT INTO Project353.LoginInfo VALUES ('"
                        + aProfile.getUserID()
                        + "','" + aProfile.getPassword()
                        + "')";

                rowCount = stmt.executeUpdate(insertString);
                stmt.executeUpdate(insertStringLogin);
                System.out.println("insert string =" + insertString);
                DBConn.close();
            } catch (SQLException e) {
                System.err.println(e.getMessage());
            }
        }

        // if insert is successful, rowCount will be set to 1 (1 row inserted successfully). Else, insert failed.
        return rowCount;
    }
```

**Update**
```java

    @Override
    public int updateProfile(ProfileBean aProfile) {
        Connection DBConn = null;
        try {
            Class.forName("org.apache.derby.jdbc.ClientDriver");
        } catch (ClassNotFoundException e) {
            System.err.println(e.getMessage());
            System.exit(0);
        }
        int rowCount = 0;
        try {
            String myDB = "jdbc:derby://localhost:1527/Project353";
            DBConn = DriverManager.getConnection(myDB, "itkstu", "student");

            String updateString;
            Statement stmt = DBConn.createStatement();

            // SQL UPDATE Syntax [http://www.w3schools.com]:
            // UPDATE table_name
            // SET column1=value, column2=value2,...
            // WHERE some_column=some_value
            // Note: Notice the WHERE clause in the UPDATE syntax. The WHERE 
            //       clause specifies which record or records that should be 
            //       updated. If you omit the WHERE clause, all records will be updated!     
            updateString = "UPDATE Project353.Users_lab3  SET "
                    + "firstname = '" + aProfile.getFirstName() + "', "
                    + "lastname = '" + aProfile.getLastName() + "', "
                    + "userID = '" + aProfile.getUserID() + "', "
                    + "password = '" + aProfile.getPassword() + "', "
                    + "email = '" + aProfile.getEmail() + "', "
                    + "secQuestion = '" + aProfile.getsecQuestion() + "', "
                    + "secAnswer = '" + aProfile.getsecAnswer() + "' "
                    + "WHERE userID = '" + aProfile.getUserID() + "'";
            
            String updateStringLogin = "UPDATE Project353.LoginInfo SET "
                    + "userID = '" + aProfile.getUserID() + "', "
                    + "password = '" + aProfile.getPassword() + "' "
                    + "WHERE userID = '" + aProfile.getUserID() + "'";
            rowCount = stmt.executeUpdate(updateString);
            stmt.executeUpdate(updateStringLogin);
            System.out.println("updateString =" + updateString);
            DBConn.close();
        } catch (SQLException e) {
            System.err.println(e.getMessage());
        }
        // if insert is successful, rowCount will be set to 1 (1 row inserted successfully). Else, insert failed.
        return rowCount;

    }
```


----------


#XML
**Why** 
One main advantage of XML over HTMl is that is allows you to create your own tags, which allows you to represent information more specifically in a way a machine can draw meaning from. XML files have "self describing data". This is much more difficult with html as is is made for creating pages for people. Another advantage is that this meta data allows for smart searches on the XML file and data.

**Difference between HTML and XML**
Same basic syntax, but xml is more expressive, allows your own tags and attributes. 

**Well-formedness vs. Validity**
A well-formed XML document simply follows the XML syntax rules. A valid document is well-formed but additionally follows the rules of its DTD or schema.

**Elements vs. Attributes**
```xml
<elementName attribute="value"></elementName>
```

**XML Schema**
 An xml schema is a document that puts constraints on what the xml document can have. It defines tags and attributes for those tags that can appear in the file. In addition, it can define datatypes for those attributes and tags.Schemas are useful because you often want to express your xml data in predicable and standard ways. If you were creating a program that parsed xml data and used it is some way all xml files would need to follow the exact same format. A schema allows you to enforce this on whoever is writting the xml file.
 
Pros of xml
- XML is more expressive than json with the use of attributes
- Using schemas the structure of an XML file can be enforced and anticipated

Pros of JSON
- JSON is shorter to write (requires less characters)
- JSON has datatypes and lists built into it
- JSON is easily loaded into javascript,where xml requires additional work


----------


#Servlets
###Why servlets? 
Servlet is an Java application programming interface (API) running on the server machine, which intercepts requests made by the client and generates/sends a response. A well known example is the HttpServlet which provides methods to hook on HTTP requests using the popular HTTP methods such as GET and POST. You can configure HttpServlets to listen on a certain HTTP URL pattern, which is configurable in web.xml, or more recently with Java EE 6, with @WebServlet annotation.

When a Servlet is first requested or during webapp startup, the servlet container will create an instance of it and keep it in memory during the webapp's lifetime. The same instance will be reused for every incoming request whose URL matches the servlet's URL pattern. You can access the request data by HttpServletRequest and handle the response by HttpServletResponse. Both objects are available as method arguments inside any of the overridden methods of HttpServlet, such as doGet() and doPost().

###get and post and their doGet and doPost methods 
xhtml page
```xml
<?xml version='1.0' encoding='UTF-8' ?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml"
      xmlns:h="http://xmlns.jcp.org/jsf/html"
      xmlns:p="http://primefaces.org/ui"
      xmlns:c="http://xmlns.jcp.org/jsp/jstl/core">
    <h:head>
        <title>Assignment 3</title>
    </h:head>
        <h:body>
        <h1>Stock Quote Entry Page Using get</h1>
        <form action="response.xhtml" method="get" enctype="multipart/form-data">
            Stock Symbol: <input type="text" name="symbol" />
            <input type="submit" value="Submit" />
        </form> 
    </h:body>
</html>
```
Java
```java
import java.io.IOException;
import java.util.List;
import javax.ejb.EJB;
import javax.faces.bean.ManagedBean;
import javax.faces.bean.SessionScoped;
import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

//WebServlet("/products")
@ManagedBean (name="response")
@SessionScoped
public class DoGet extends HttpServlet {

    private float currentTradePrice;
    private String stockSymbol;
    
    public float getCurrentTradePrice() {
        return this.currentTradePrice;
    }
    
    @Override
    public void doGet(HttpServletRequest req, HttpServletResponse res) throws ServletException, IOException  {
        //stockSymbol = req.getParameter("symbol");
        webservice.StockQuoteWSService service = new webservice.StockQuoteWSService();
        webservice.StockQuoteWS port = service.getStockQuoteWSPort();
        this.currentTradePrice = port.getTradePrice(req.getParameter("symbol"));
    }

	    @Override
    public void doPost(HttpServletRequest req, HttpServletResponse res) throws ServletException, IOException  {
    ...
    }
}
```

----------


#Web Services, Security, AJAX, and other materials covered before test
###Web Security 
**SQL Injection **
SQL injection is a code injection technique, used to attack data-driven applications, in which malicious SQL statements are inserted into an entry field for execution (e.g. to dump the database contents to the attacker). SQL injection must exploit a security vulnerability in an application's software, for example, when user input is either incorrectly filtered for string literal escape characters embedded in SQL statements or user input is not strongly typed and unexpectedly executed." 
**Fixit**
```java
// The ? below are parameters (i.e., placeholders) to the query and are resolved
// in the setString method below
String queryString = "select * from restaurantDB.Users where USERNAME = ? and PASSWORD = ?";

// Note the use of a diff class, called PreparedStatement
PreparedStatement pstmt = DBConn.prepareStatement( queryString );
pstmt.setString( 1, username); // replace the 1st ? with username
pstmt.setString( 2, password); // replace the 2nd ? with password
ResultSet rs = pstmt.executeQuery( );
```

**Cross-site Scripting**
Cross-site scripting (XSS) is a type of computer security vulnerability typically found in web applications. XSS enables attackers to inject client-side script into web pages viewed by other users. A cross-site scripting vulnerability may be used by attackers to bypass access controls such as the same-origin policy. Inject html/css/javascript into site through unchecked textbox. 

###Web Services
**Creating a web service**
```java
import javax.jws.WebService;

@WebService
public class Name {
	...
}
```
**Consuming a web service**
```java
public static void main(String[] args) {
        // TODO code application logic here
        String queryTerm = "java";
        String searchLocation = "chicago";
        int radius = 100;
        int daysBack = 20;
        String searchCountry = SearchCountry.US.toString().toLowerCase();
        String sortCriteria = SortCriteria.RELEVANCE.toString().toLowerCase();
        String websiteType = WebsiteType.JOBSITE.toString().toLowerCase();
        String jobType = JobType.FULLTIME.toString().toLowerCase();
        List <JobSearchResult> jobSearchResults = searchJobsAdvanced(queryTerm,
        searchLocation, radius, searchCountry, sortCriteria, daysBack, websiteType, jobType);
        int counter = 1;
        for (JobSearchResult jobSearchResult : jobSearchResults) {
            System.out.println("Job Search Result #" + counter);
            System.out.println("Job Title: " + jobSearchResult.getTitle());
            System.out.println("Company: " + jobSearchResult.getCompany());
            System.out.println("Snippet: " + jobSearchResult.getSnippet());
            System.out.println("City: " + jobSearchResult.getCity());
            System.out.println("State: " + jobSearchResult.getState());
            System.out.println("Country: " + jobSearchResult.getCountry());
            System.out.println("Location: " + jobSearchResult.getLocation());
            System.out.println("Latitude: " + jobSearchResult.getLatitude());
            System.out.println("Longitude: " + jobSearchResult.getLongitude());
            System.out.println("Date Posted: " + jobSearchResult.getDatePosted());
            System.out.println("Posted: " + jobSearchResult.getDaysPostedAgo());
            System.out.println("Source: " + jobSearchResult.getSource());
            System.out.println("URL: " + jobSearchResult.getURL() + "\n");
            counter++;
        }
    }
```


----------


#Patterns 
**MVC =** model view controller
**DAO =** Data Acess Object 
**CDI =** Context Dependancy Injection

#Random Question 
**How do you augment the following code segment (previously discussed in class) to prevent SQL Injection? Devise your answer, print it out, and bring it to class on the day of the test.**
```java
String queryStr = "Select count(*) from IdPassword where Id = " +   userName + " and Password = ‘ " + password + " ‘ ";  
rs = stmt.executeQuery(queryStr); 
// if login info is invalid, rs will have a row and the count will be 0. 
// Else, login is good. 
rs.next(); // get the count 
if (rs.getInt(1) == 0)   
   outStr += "Your login info is incorrect. Try again."; 
else   
   outStr += "Welcome back," + userName + ". Please buy something this time :)";
```
