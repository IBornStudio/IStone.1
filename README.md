# IStone.1

# Auto detect text files and perform LF normalization
* text=auto

public class SanitizeText {
    
    // Method to sanitize emails
    public static String sanitizeEmail(String email) {
        String sanitizedEmail = "";
        for (int i = 0; i < email.length(); i++) {
            if (email.charAt(i) == '@') {
                sanitizedEmail += " [at] ";
            } else if (email.charAt(i) == '.') {
                sanitizedEmail += " [dot] ";
            } else {
                sanitizedEmail += email.charAt(i);
            }
        }
 
        return sanitizedEmail;
  }
  
  // Method to sanitize URLs
  public static String sanitizeURL(String url) {
        String sanitizedURL = "";
        for (int i = 0; i < url.length(); i++) {
            if (url.charAt(i) == '.') {
                sanitizedURL += " [dot] ";
            } else {
                sanitizedURL += url.charAt(i);
            }
 
  }
  
  // Front end code
  <html>
  <head>
    <title>Sanitize Text</title>
  </head>
  <body>
    <form action="sanitize.php" method="post">
      Enter Email: <input type="text" name="email" />
      <input type="submit" value="Sanitize Email" />
    </form>
    <form action="sanitize.php" method="post">
      Enter URL: <input type="text" name="url" />
      <input type="submit" value="Sanitize URL" />
    </form>
  </body>
  </html>
  
  // Back end code 
  <?php
    if (isset($_POST['email'])) {
        $email = $_POST['email'];
        echo SanitizeText::sanitizeEmail($email);
    }
 
    if (isset($_POST['url'])) {
        $url = $_POST['url'];
        echo SanitizeText::sanitizeURL($url);
    }
  ?>
  
  // Run the application 
  java SanitizeText
 // Output 
   
   // Add a drop-down menu
   <form action="sanitize.php" method="post">
      Select Information to Sanitize: 
      <select name="info">
        <option value="email">Email</option>
        <option value="url">URL</option>
        <option value="phone">Phone Number</option>
        <option value="creditcard">Credit Card Number</option>
      </select>
      <input type="text" name="data" />
      <input type="submit" value="Sanitize" />
    </form>
    
    // Back end code 
    <?php
      if (isset($_POST['info'])) {
          $info = $_POST['info'];
          $data = $_POST['data'];
          if ($info == 'email') {
              echo SanitizeText::sanitizeEmail($data);
          } else if ($info == 'url') {
              echo SanitizeText::sanitizeURL($data);
          } else if ($info == 'phone') {
              echo SanitizeText::sanitizePhoneNumber($data);
          } else if ($info == 'creditcard') {
              echo SanitizeText::sanitizeCreditCardNumber($data);
          }
      }
    ?>
    
    // Add a new method to freeze any inbound links 
    public static String freezeInboundLinks(String url) {
        String frozenURL = "";
        for (int i = 0; i < url.length(); i++) {
            if (url.charAt(i) == '.') {
                frozenURL += " [dot] ";
            } else if (url.charAt(i) == ':') {
        frozenURL += " [colon] ";
      } else if (url.charAt(i) == '/') {
        frozenURL += " [slash] ";
      } else {
                frozenURL += url.charAt(i);
            }
        }
 
        return frozenURL;
  }
  
  // Add a new method to warn and alert users with red colour features
  public static String warnAndAlertUsers(String message) {
    String alertMessage = "";
    for (int i = 0; i < message.length(); i++) {
      if (message.charAt(i) == '<') {
        alertMessage += "<span style='color: red;'> [bug detected] </span>";
      } else {
        alert
