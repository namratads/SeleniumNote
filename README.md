Q 1] What is the Selenium?

==> Selenium is an open-source automation testing framework used for testing web applications across different browsers and platforms.

It provides a suite of tools that cater to different automation testing needs, making it a popular choice among testers for both functional and regression testing of web applications.

Q 2] What are the component of Selenium?

==> Selenium is composed of several components, each serving a specific purpose in the overall framework for automating web applications. These components are:

 ---1) Selenium IDE :  For record-and-playback of test cases.
    
 ---2) Selenium RC : An older component, now replaced by WebDriver.
    
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

1. Cross-Browser Compatibility
  
   --Chrome / Firefox / Edge / Safari
   
2. Cross-Platform Testing
  
   --Windows / macOS / Linux
   
3. Supports Multiple Programming Languages

   --Java, Python, C#, Ruby, JavaScript, and Kotlin--allows testers and developers to write test scripts in the language as per their choice
   
4. Direct Interaction with Browsers

   --WebDriver communicates directly with the web browser, which leads to faster execution of tests compared to older tools like Selenium RC
   
5. Handling Dynamic Web Content

    --WebDriver is capable of handling modern web technologies and dynamic content that can change without a page reload.

    -- It can wait for elements to appear or become clickable before interacting with them, which improves the reliability of test scripts.

6. Wide Range of Web Element Locators

    -- provides multiple ways to locate elements on a web page

    --This flexibility in locating elements helps testers write precise and robust test scripts.

7. Integration with Testing Frameworks

    -- can be easily integrated with popular testing frameworks such as JUnit, TestNG, NUnit, and others.

    -- This allows for better test management, reporting, and the ability to structure tests in a more organized way.
    
8.  Open Source and Free


9.  Supports Parallel Test Execution

     -- Selenium WebDriver can be used with Selenium Grid to execute tests in parallel across multiple browsers and machines.

     -- This capability significantly reduces the time required to execute large test suites.


10.  Rich Ecosystem and Tool Integration


11.  Scalability

     --can be used for both small and large projects. 

     --It can handle simple test cases as well as complex workflows involving multiple pages and elements.

12.  Support for Browser Extensions

13.   Extensive Documentation and Community Support

While Selenium WebDriver is a powerful and widely-used tool for web automation testing, it does have some disadvantages and limitations.

1. Limited to Web Applications :

   --can only be used to test web applications.
   
   --cannot be used for testing desktop applications, mobile applications

2. No Built-in Reporting

 -- Manual Setup Required: Selenium WebDriver does not come with built-in reporting capabilities.
 
 -- Testers need to integrate it with third-party tools or frameworks (like TestNG, JUnit, or custom solutions) to generate test reports.

 -- This requires additional setup and configuration.
 











Q 5] What is the Architecture of selenium WebDriver?

--The architecture of Selenium WebDriver is designed to be modular, allowing it to interact directly with web browsers in a flexible and efficient manner.

--Understanding this architecture helps in grasping how Selenium WebDriver operates and how it manages communication between test scripts and web browsers.

1. Selenium Client Libraries :

--the language-specific bindings that allow users to write test scripts in different programming languages--Java, Python, C#, Ruby, JavaScript.

--translate the test scripts written in these languages into HTTP requests that can be understood by the browser drivers.

2. JSON Wire Protocol / W3C WebDriver Protocol :
   
-- which allows the client libraries to send commands to and receive responses from the browser driver.

-- Protocols for communication between client libraries and browser drivers.

3. Browser Drivers :
   
-- Each browser has its own browser driver

-- browser driver acts as a bridge between the Selenium commands (sent via JSON or W3C protocol) and the browser.

-- It receives the HTTP requests from the client libraries, interprets them, and then executes the corresponding actions in the web browser.

--  Interface between the Selenium commands and the web browser.

4. Web Browser :
   
-- The environment where the actual testing takes place.

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



Q 6] How to Launch Browser in WebDriver?

In Selenium 3,
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
3] Launch EdgeBrowser(Internet) : 

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

   In Selenium 4, if you want to launch browser then,
 
    WebDriver driver = new ChromeDriver();
OR
   
    WebDriver driver = new FirefoxDriver();
OR

    WebDriver driver = new EdgeDriver();


Q 7] What is WebDriverManager ?

WebDriverManager is a Java library that automates the management of browser drivers, 
such as ChromeDriver, GeckoDriver (for Firefox)and others, 
which are required by Selenium WebDriver to control web browsers.
WebDriverManager automatically handles browser updates and driver versions.


Q 8] How to Open URL?
         
    driver.get(“pass the application url”);
 OR
           
    driver.navigate().to(“pass the application url”);

Q 9] How to Capture Title of Web Page?
 

    System.out.println("The Title of WebPage is : " + driver.getTitle());

Q 10] How to Capture URL of Web Page?

    System.out.println("The URL of WebPage is : " + driver.getCurrentUrl());

Q 11] How to Capture Page-source of Web Page?          

    System.out.println("The Page-source of WebPage is : " + driver.getPageSource());

Q 12] How to check WebElement is Displayed , Enabled and Selected?

Demo website  =   https://demo.nopcommerce.com/register

    WebElement wb = driver.findElement(By.xpath(“—xpath--”));
    System.out.println(wb.isDisplayed());--------true/false
    System.out.println(wb.isEnabled());--------true/false
Selected() is used for RadioButton/DropDown/CheckBoxes is selected or not

    WebElement wb = driver.findElement(By.xpath(“—xpath--”));
    System.out.println(wb.isSelected());--------true/false

Q 13] How to Navigate Back and Forward? 
 Here we want to 2 websites
 Demo website  =   https://www.amazon.in/    and     https://www.snapdeal.com/ 

    driver.navigate().back();
    driver.navigate().forward();

Q 14] How to Refresh or Reload page?
  
    driver.navigate().refresh();

Q 15] What is the difference between get(); and navigate().to();?


Feature-----------------get();---------------------------------navigate().to();

1]Wait Behavior	        1]Waits for the entire page to load      1]Does not always wait for full page load

2]History Handling	2]Does not maintain browser history      2]Maintains browser history, useful for navigating back/forward

3]Additional Actions	3]Only opens URL	                 3]Can navigate back, forward, refresh in addition to opening URL


Q 16] What is the difference between findElement(); and findElements(); in Selenium WebDriver?

findElement(); method 

---used to locate a single web element on the web page.

---returns Single WebElement or first matching element.

---if not found then throwsNoSuchElementException

    Driver.findElement(By.xpath(“—xpath--”));
findElements(); method 

---used to locate multiple web elements that match the locator.

---Returns a List<WebElement> of all matching elements.

---If no elements are found, it returns an empty list (does not throw an exception)
   --size();method--just return 0 (not throws any exception)
   
---if xpath of only one WebElement pass then it will return one WebElement. 
    
    Driver.findElements(By.xpath(“—xpath--”));
---Here we get multiple elements so when we want to get it one by one name for print then we should go for for-each loop .
    
    For(WebElement wb : varableoflist ) 
    {
                System.out.println(Wb.getText());   
    }

Q 17] How to clear old text from Input Box and provide new text in Input Box?
  or Q] How to provide and clear text from input box?
  
--sendKeys() is used to type or input text into an element.

--clear() removes any existing text from a text input field.
      
    WebElement wb = driver.findElement(By.xpath(“—xpath--”));
    System.out.println(wb.clear());------it will return clear Text from Input Box
    System.out.println(wb.sendKeys(“—someText--”));

Q 18] How to Capture Text from Input Box?
     
    System.out.println(wb.getAttribute(“value”));  ------it will return default Text from Input Box
    
Note : we cannot use .getText() method b’coz it return innertext of webelement(which in black color) in DOM.

Q 19] What is the difference between getText() and getAttribute("value")?

--both used to retrieve information from a web element, but they serve different purposes 

  i)getText()
  
   --retrieves the visible text of a web element (i.e., the text between the opening and closing tags of an element).
   
   --Returns a String containing the visible text of the element.
   
   --Used when you want to capture the displayed text on the screen for elements
   
  ii)getAttribute("value")
  
   --retrieves the value of a specific attribute (such as "value", "href", "class", etc.) from a web element.
   
   --Returns a String containing the value of the specified attribute.
   
Q 20] How to handle Drpdown in Selenium WebDriver?

Here Select class which is provided by Selenium WebDriver, when WebElement having Select TagName then we can handle that webelement by three different ways.


Locate the dropdown element

    WebElement dropdown = driver.findElement(By.id("dropdownID"));
Create an instance of the Select class

    Select select = new Select(dropdown);
i)Select an option by visible text

    select.selectByVisibleText("Option Text");
ii)Select an option by value attribute

    select.selectByValue("optionValue");
iii)Select an option by index (index starts at 0)

    select.selectByIndex(2);

Get the first selected option and print its text

    WebElement selectedOption = select.getFirstSelectedOption();
    System.out.println("Selected option: " + selectedOption.getText());

Get all options in the dropdown
    
    List<WebElement> options = select.getOptions();
    for (WebElement option : options) 
    {
    System.out.println("Option: " + option.getText());
    }

Q 21] What is the use of Select class?

--The Select class in Selenium WebDriver is specifically designed to handle HTML <select> elements, which represent dropdown menus. 

--It provides methods to easily interact with single-selection and multi-selection dropdowns by selecting or deselecting options.

    1).selectByVisibleText();
    //Selects an option based on the visible text of the option.
    //parameter-text
    // return type is void
    
    2).selectByValue();
    //Selects an option whose value attribute matches the specified string.
    //parameter-value
    // return type is void
    
    3).selectByIndex();
    //Selects an option based on its index (the position of the option in the dropdown, starting from 0).
    //parameter-index
    // return type is void
    
    4).isMultiple();
    //To check if the dropdown is a multi-select dropdown, meaning that it allows the user to select more than one option at a time.
    //Return type is boolean(Returns true if the dropdown allows multiple selections; otherwise, returns false).
    
    5).deselectByVisibleText();
    //Deselects an option based on the visible text of the option (only works for multi-select dropdowns).
    //parameter-text
    // return type is void
    
    6).deselectByValue();
    //Deselects an option whose value attribute matches the specified string (only works for multi-select dropdowns).
    //parameter-value
    // return type is void
    
    7).deselectByIndex();
    //Deselects an option based on its index (the position of the option in the dropdown, starting from 0) in a multi-select dropdown.
    //parameter-index
    // return type is void
    
    8).deselectAll();
    //Deselects all selected options in a multi-select dropdown.
    // return type is void
    
    9).getAllSelectedOptions();
    //Returns a list of all selected options in a dropdown (works for both single and multi-select dropdowns).
    //Return Type: List<WebElement> (A list of WebElement objects that are currently selected).
    
    10).getOptions();
    //Returns a list of all options available in the dropdown
    //Return type is List<WebElement> (A list of all the WebElement options in the dropdown).

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




Q 22] How to handle Multiple Dropdowns in a WebPage? 
or Q] How to handle Multiple Dropdowns in a WebPage using generic method?

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


Q 23] How to handle Bootstrap Dropdown in Selenium WebDriver?

Bootstrap Dropdown means here Select Tag is not available to Dropdown and WebElement look like button but it is actually Dropdown.

Bootstrap dropdowns are generally made of <div>, <ul>, and <li> elements. 

To handle them, you first need to click on the dropdown element to reveal the list, and then interact with the list items.

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

















