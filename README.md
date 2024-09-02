Q 1] What is the Selenium?

==> Selenium is an open-source automation testing framework used for testing web applications across different browsers and platforms.

It provides a suite of tools that cater to different automation testing needs, making it a popular choice among testers for both functional and regression testing of web applications.

Q 2] What are the component of Selenium?

==> Selenium is composed of several components, each serving a specific purpose in the overall framework for automating web applications. These components are:

 ---1) Selenium IDE :  For record-and-playback of test cases.
    
 ---2) Selenium RC :An older component, now replaced by WebDriver.
    
 ---3) Selenium Grid : For distributed and parallel test execution.
    
 --- 4) Selenium WebDriver : For writing code-based automation scripts.
   
  These components can be used individually or together, depending on the testing requirements and the complexity of the web application under test.


Q 3] What is WebDriver?  

==>

WebDriver is a Interface------Chrome,firefox,edge n so on are the implementation classes.

Selenium WebDriver is a core component of the Selenium framework, designed to automate web application testing by controlling web browsers directly. 

It is widely used by testers and developers to interact with web pages as a user would, allowing for the automation of repetitive tasks.

Key Features

1] Browser Interaction

2] Multi-Browser Support

3] Cross-Platform Testing

4] Programming Language Support

5] Element Locators

6] Handling Dynamic Web Content

7] No Need for a Selenium Server

8] Support for Browser Automation Frameworks
    

Q 4] What are the advantages and disadvantage of Selenium WebDriver?

==>

Selenium WebDriver offers several advantages that make it a popular choice for web application automation testing. Here are some of the key benefits:

1. Cross-Browser Compatibility--Chrome / Firefox / Edge / Safari
2. Cross-Platform Testing--Windows / macOS / Linux
3. Supports Multiple Programming Languages--Java, Python, C#, Ruby, JavaScript, and Kotlin--allows testers and developers to write test scripts in the language as per thier choice
4. Direct Interaction with Browsers--WebDriver communicates directly with the web browser, which leads to faster execution of tests compared to older tools like Selenium RC 
5. Handling Dynamic Web Content
6. Wide Range of Web Element Locators
7. Integration with Testing Frameworks
8.  Open Source and Free
9.  Supports Parallel Test Execution
10.  Rich Ecosystem and Tool Integration
11.  Scalability
12.  Support for Browser Extensions
13.   Extensive Documentation and Community SupportQ 1] What is the Selenium?

Q 5] What is the Architecture of semenium WebDriver?


The architecture of Selenium WebDriver is designed to be modular, allowing it to interact directly with web browsers in a flexible and efficient manner.

Understanding this architecture helps in grasping how Selenium WebDriver operates and how it manages communication between test scripts and web browsers.

1. Selenium Client Libraries :

--the language-specific bindings that allow users to write test scripts in different programming languages--Java, Python, C#, Ruby, JavaScript.

--translate the test scripts written in these languages into HTTP requests that can be understood by the browser drivers.

4. JSON Wire Protocol / W3C WebDriver Protocol :
   
-- which allows the client libraries to send commands to and receive responses from the browser driver.

-- Protocols for communication between client libraries and browser drivers.

6. Browser Drivers :
   
-- Each browser has its own browser driver

-- browser driver acts as a bridge between the Selenium commands (sent via JSON or W3C protocol) and the browser.

-- It receives the HTTP requests from the client libraries, interprets them, and then executes the corresponding actions in the web browser.

--  Interface between the Selenium commands and the web browser.

8. Web Browser :
   
--The environment where the actual testing takes place.

-- driver interacts with the browser to perform actions such as navigating to a URL, clicking elements, entering text, and extracting information.

   
*************Detailed Workflow of Selenium WebDriver Architecture:

1] Test Script Execution:

The tester writes a test script in a language supported by Selenium using the Selenium Client Libraries.

2] Command Translation:

The client libraries convert the commands in the test script into a format that can be sent to the browser driver. 

This involves using the JSON Wire Protocol or W3C WebDriver Protocol to create HTTP requests.

3] HTTP Request Sent to Browser Driver:

The formatted HTTP requests are sent to the corresponding browser driver (e.g., ChromeDriver for Chrome).

4] Browser Driver Interaction:

The browser driver receives the HTTP requests, interprets them, and sends the appropriate commands to the web browser to perform the desired actions (e.g., clicking a button, entering text, etc.).

5] Browser Execution:

The web browser executes the commands and performs the required actions on the web page.

6] Response Handling:

After executing the commands, the browser sends a response back to the browser driver.

7] Response Sent to Client Libraries:

The browser driver converts the response into an HTTP response, which is then sent back to the client libraries.

8] Result Processing:

The client libraries process the response and provide the results (e.g., success/failure, returned data) to the test script, allowing the tester to analyze the outcome of the test.

9] Diagram of Selenium WebDriver Architecture:



Q] How to Launch Browser?


    1] Launch ChromeBrowser : 
                 System.setProperty(“key”,”value”);
                                      Key  webdriver.chrome.driver
                                      Value path of chromedriver.exe\\chromedriver.exe 
                WebDriver driver = new ChromeDriver();
        2] Launch FirefoxBrowser : 
                             System.setProperty(“key”,”value”);
                                                  Key  webdriver.gecko.driver
                                                  Value path of geckodriver.exe\\geckodriver.exe 
                            WebDriver driver = new FirefoxDriver();
         3]     Launch EdgeBrowser(Internet) : 
                           System.setProperty(“key”,”value”);
                                              Key  webdriver.edge.driver
                                              Value path of edgedriver.exe\\msedgedriver.exe 
                           WebDriver driver = new EdgeDriver();
Suppose , I don’t want download this drivers manually, then hear one more approach 
Just copy the WebDriverManager dependency from Maven Depository and paste in pom.xml file in our Maven Project.
 Launch ChromeBrowser : 
 
                 WebDriverManager.chromedriver().setup();
                     WebDriver driver = new ChromeDriver();
 OR
 Launch FirefoxBrowser :
                     
		       WebDriverManager.firefoxdriver().setup();
	                WebDriver driver = new FirefoxDriver();
OR
  
 Launch EdgeBrowser(Internet) :
 
                      WebDriverManager.edgedriver().setup();
          
                         WebDriver driver = new EdgeDriver();
Q] How to Open URL?
  
         
	    driver.get(“pass the application url”);
 OR
          
	    driver.navigate().to(“pass the application url”);

Q] How to Capture Title of Web Page?
  

         System.out.println("The Title of WebPage is : " + driver.getTitle());

Q] How to Capture URL of Web Page?
 

          System.out.println("The URL of WebPage is : " + driver.getCurrentUrl());

Q] How to Capture Page-source of Web Page?
             

          System.out.println("The Page-source of WebPage is : " + driver.getPageSource());

Q] How to check WebElement is Displayed , Enabled and Selected?
 
Demo website  =   https://demo.nopcommerce.com/register


          WebElement wb = driver.findElement(By.xpath(“—xpath--”));
          System.out.println(wb.isDisplayed());--------true/false
          System.out.println(wb.isEnabled());--------true/false
          Selected() is used for RadioButton/DropDown/CheckBoxes is selected or not
          WebElement wb = driver.findElement(By.xpath(“—xpath--”));
          System.out.println(wb.isSelected());--------true/false



Q] How to Navigate Back and Forward? How to Refresh or Reload page?
 Here we want to 2 websites
           
	   Demo website  =   https://www.amazon.in/    and     https://www.snapdeal.com/ 
           driver.navigate().back();
           driver.navigate().forward();
           driver.navigate().refresh();

Q] findElement();  method -------returns Single WebElement---if not found then throwsNoSuchElementException


     Driver.findElement(By.xpath(“—xpath--”));
    findElements();  method -----returns MultipleWebElements---List< WebElement >------if xpath of only one WebElement pass then it will return one WebElement--------if not found then  
    size();  method  just return 0 (not throws any exception)
    Driver.findElements(By.xpath(“—xpath--”));
     Here we get multiple elements so when we want to get it one by one name for print then we should go for for-each loop .
    For(WebElement wb : varableoflist ) {
                System.out.println(Wb.getText());     }

Q] How to clear old text from Input Box and provide new text in Input Box?
      
      WebElement wb = driver.findElement(By.xpath(“—xpath--”));
      System.out.println(wb.clear());------it will return clear Text from Input Box
      System.out.println(wb.sendKeys(“—someText--”));
Q] How to Capture Text from Input Box?
     
     System.out.println(wb.getAttribute(“value”));  ------it will return default Text from Input Box
Note : we cannot use .getText() method b’coz it return innertext of webelement(which in black color) in DOM.
Q] How to handle Drpdown in Selenium WebDriver?
Here Select class which is provided by Selenium WebDriver, when WebElement having Select TagName then we can handle that webelement by three different ways.


  1)	 .selectByVisibleText();
  2)	 . selectByValue();
  3)	 . selectByIndex();
•	Above all these way use to select one option from Dropdown

    Demo website  =   https://www.opencart.com/index.php?route=account/register
    WebElement wb = driver.findElement(By.xpath(“—xpath--”));-----webelement of Dropdown
 // Create a Select class object to select one option from Dropdown
          
	   Select s = new Select(wb);
           wb.selectByVisibleText(); 
                     OR
           wb.selectByValue(); 
                     OR
           wb.selectByIndex();
// Create a Select class object & without using Select class methods how  select one option from Dropdown

    WebElement wb1 = driver.findElement(By.xpath(“—xpath--”));-----webelement of Dropdown
    Select s = new Select(wb1);
    List<WebElement> l = s.getOptions();
		for(WebElement wb : l)
			{
				if(wb.getText().equals("oneoptionfromDropdown"))
				{
					wb.click();
					break;
				}
			}




Q] How to handle Multiple Dropdowns in a WebPage? 

    Demo website  =  https://formstone.it/components/dropdown/demo/ 
    Demo website  =   https://admirhodzic.github.io/multiselect-dropdown/demo.html

Aproach1 : with Select class ---------it is a lengthy aprroach

    WebElement wb1 = driver.findElement(By.xpath(“—xpath--”));---webelement of Dropdown1
    Select dropdown1 = new Select(wb1);

    WebElement wb2 = driver.findElement(By.xpath(“—xpath--”));---webelement of Dropdown2
    Select dropdown2 = new Select(wb2);

    WebElement wb3 = driver.findElement(By.xpath(“—xpath--”));---webelement of Dropdown3
    Select dropdown3 = new Select(wb3);

    WebElement wb4 = driver.findElement(By.xpath(“—xpath--”));---webelement of Dropdown4
    Select dropdown4 = new Select(wb4);


Aproach2: by using Generic method----here not need to create Select class object

    WebElement wb1 = driver.findElement(By.xpath(“—xpath--”));---webelement of Dropdown1
    getOptFromDropdown(wb1,“value”);  

    WebElement wb2 = driver.findElement(By.xpath(“—xpath--”));---webelement of Dropdown2 
    getOptFromDropdown(wb2,“value”);  

    WebElement wb3 = driver.findElement(By.xpath(“—xpath--”));---webelement of Dropdown3
    getOptFromDropdown(wb3,“value”);  
//write Generic method

    Public static void getOptFromDropdown(WebElement wb,String value)  {
          Select s = new Select(wb);
          List<WebElement> l = s.getOptions();
		for(WebElement e : l)
			{
				if(e.getText().equals(value))
				{
					e.click();
					break;
				}
			}


Q] How to handle Bootstrap Dropdown in Selenium WebDriver?

Bootstrap Dropdown means here Select Tag is not available to Dropdown and WebElement look like button but it is actually Dropdown.

    driver.findElement(By.xpath(“—xpath--”)).click();---wb of Dropdown
    List<WebElement> l = driver.findElements(By.xpath(“—xpath--”));-----------------list of wb of Bootstrap dropdown
    System.out.println(“No. of Option in Bootstrap Dropdown”+wb.size());
    for(WebElement e : l)
			{
				if(e.getText().equals(“value”))
				{
					e.click();
					break;
				}
			}
If webpage have multiple Bootstrap Dropdown then we should go for Generic method


Q] How to handle jQuery Dropdown in Selenium WebDriver?

    Demo website = https://www.jqueryscript.net/demo/Drop-Down-Combo-Tree/

Here ,  In jQuery Dropdown, we can select one option or more option or all option

Here we have to use Generic method to handle the jQuery Dropdown
         
	 driver.findElement(By.xpath(“—xpath--”)).click();---wb of jQuery Dropdown
    getOptFromDropdown(wb1,“value”);  
OR
   
    getOptFromDropdown(wb1,“value”,“value”,“value”);  
OR

    getOptFromDropdown(wb1,“all”);  

     List<WebElement> l = driver.findElements(By.xpath(“—xpath--”));----------------------list of wb of jQuery dropdown
//write Generic method

    Public static void getOptFromDropdown(WebElement wb,String… value)  {
          Select s = new Select(wb);
          List<WebElement> l = s.getOptions();
		for(WebElement e : l)
			{
				if(e.getText().equals(value))
				{
					e.click();
					break;
				}
			}


 
Q] How to handle JavaScript ALerts

    driver.switchTo().alert().accept();
    
Q] How to handle Authentication pop-ups



Q] How to handle permission based pop-ups

















