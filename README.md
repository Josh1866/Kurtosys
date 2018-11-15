# Kurtosys
Test
Functional UI Test ( I manage to teach myself selenium over 2 days and i got stuck with the code and only manage to get this done 
---
package co.kurtosys.selenium.webdriver.basic;
import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
public class Day1 {
	static WebDriver driver;
	JavascriptExecutor jse;
	JavascriptExecutor go;
	WebElement Searchbox;
	public void invokeBrowser( Object actions, Object element, Object checkboxes ) {
		try {
			System.setProperty( "webdriver.chrome.driver", "C:\\Users\\joshua.kinnear\\Desktop\\Test\\chromedriver.exe" );
			//This driver will insure that the browser open successfully;
			
			
			driver = new ChromeDriver();
			//The need to maximize the browser is a need to demonstrate the test;
			//The browser will endure for the testing of the test;
			
			
			driver.manage()
				.window()
				.maximize();
			
		//The driver will successfully open the browser below for testing purposes and test the scripts accordingly.
		//I use the xpath to method to accept the disclaimer.
	    //I also find the dynamic link by using the linktext method to get the title of the function.
			
			
			driver.get( "https://am.jpmorgan.com/gb/en/asset-management/gim/adv/home" );
			driver.findElement( By.xpath( "//*[@id=\"ng-app\"]/body/div[5]/div/div/div/div/div[2]/div[4]/div[2]/div" ) )
				.click();
			jse = ( JavascriptExecutor ) driver;
			String currentURL = driver.getCurrentUrl();
			driver.get( currentURL );
			driver.findElement( By.linkText( "Find a fund" ) )
				.click();
			System.out.println( "Title of page is:" + driver.getTitle() );
			System.out.print( currentURL );
			
			
			//The method below will endure you to navigate to the content needed as per test to locate it to get a successful test.
			//This will insure the checkbox is tick and function will search the particular content which is needed for a sucessful test.
			//I added the sleep option for the browser to sleep for 5secs before selecting the next content as per the test requirements.
			
			
			driver.findElement( By.xpath( "//*[@id=\"content\"]/div[2]/div/div[1]/div[2]/div[2]/div[1]/div[1]/div[2]/div[3]/div/div/div/ul/li[1]/label" ) )
				.getLocation();
			driver.findElement( By.xpath( "//*[@id=\"f-Investment Trusts\"]" ) )
				.isSelected();
			driver.findElement( By.xpath( "//*[@id=\"f-Investment Trusts\"]" ) )
				.click();
			System.out.print( currentURL );
			driver.findElement( By.xpath( "//*[@id=\"content\"]/div[2]/div/div[1]/div[2]/div[1]/div/input" ) )
				.getLocation();
			driver.findElement( By.xpath( "//*[@id=\"content\"]/div[2]/div/div[1]/div[2]/div[1]/div/input" ) )
				.sendKeys( "LU0210527791" );
			driver.findElement( By.xpath( "//*[@id=\"content\"]/div[2]/div/div[1]/div[2]/div[1]/div/a/i" ) )
				.click();
			Thread.sleep( 5000 );
			
			
			
			//This option will navigate to the content searched and will display the graphs as per rest requirements.
			//Now i can verify if the test is sucessful.
			
			
			driver.findElement( By.xpath( "//td[@class='ng-scope dotdotdot']//*[@class='ng-binding']" ) )
				.click();
			driver.findElement( By.id( "PerformanceLi" ) )
				.click();
		} catch ( Exception e ) {
			e.printStackTrace();
		}
	}
	public static void main( String[] args ) {
		Day1 myObj = new Day1();
		myObj.invokeBrowser( myObj, myObj, myObj );
	}
}
       
       
	


       




Functional API Test
---

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
pm.test("Body matches string", function () {
    pm.expect(pm.response.text()).to.include("data").to.contain("records")>0;
});

pm.test("Body matches string", function () {
    pm.expect(pm.response.text()).to.include("JPMorgan");
});

