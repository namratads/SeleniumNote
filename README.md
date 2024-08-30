WebDriver is a Interface------Chrome,firefox,edge n so on are the implementation classes.
Q] How to Launch Browser?
  1] Launch ChromeBrowser : 
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
 Launch ChromeBrowser :  WebDriverManager.chromedriver().setup();
                     WebDriver driver = new ChromeDriver();
                            OR
 Launch FirefoxBrowser :  WebDriverManager.firefoxdriver().setup();
	             WebDriver driver = new FirefoxDriver();
                            OR
   Launch EdgeBrowser(Internet) : WebDriverManager.edgedriver().setup();
          
                         WebDriver driver = new EdgeDriver();
Q] How to Open URL?
  driver.get(“pass the application url”);
                         OR
        driver.navigate().to(“pass the application url”);

Q] How to Capture Title of Web Page?
 System.out.println("The Title of WebPage is : " + driver.getTitle());

Q] How to Capture URL of Web Page?
 System.out.println("The URL of WebPage is : " + driver.getCurrentUrl());

Q] How to Capture Page-source of Web Page?
 System.out.println("The Page-source of WebPage is : " + driver.getPageSource());

Q] How to check WebElement is Displayed , Enabled and Selected?
 Demo website  =   https://demo.nopcommerce.com/register
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
 findElements();  method -----returns MultipleWebElements---List< WebElement >------if xpath of only one WebElement pass then it will return one WebElement--------if not found then  size();  method  just return 0 (not throws any exception)
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
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
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
List<WebElement> l = driver.findElements(By.xpath(“—xpath--”));---------------------------------------------------------------------------list of wb of Bootstrap dropdown
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

List<WebElement> l = driver.findElements(By.xpath(“—xpath--”));---------------------------------------------------------------------------list of wb of jQuery dropdown
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




