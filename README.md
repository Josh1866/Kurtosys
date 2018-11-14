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
	

	
	public void invokeBrowser(Object actions, Object element, Object checkboxes) {
		
		try {
			System.setProperty("webdriver.chrome.driver", "C:\\Users\\joshua.kinnear\\Desktop\\Test\\chromedriver.exe");
			driver = new ChromeDriver();
			driver.manage().window().maximize();
			
			
			driver.get("https://am.jpmorgan.com/gb/en/asset-management/gim/adv/home");
			 driver.findElement(By.xpath("//*[@id=\"ng-app\"]/body/div[5]/div/div/div/div/div[2]/div[4]/div[2]/div")).click();
			 jse = (JavascriptExecutor)driver;
			 String currentURL = driver.getCurrentUrl();
			driver.get(currentURL);
			 driver.findElement(By.linkText("Find a fund")).click();
			 System.out.println("Title of page is:" + driver.getTitle());
			 System.out.print(currentURL);
			 driver.findElement(By.xpath("//*[@id=\"content\"]/div[2]/div/div[1]/div[2]/div[2]/div[1]/div[1]/div[2]/div[3]/div/div/div/ul/li[1]/label")).getLocation();
			 driver.findElement(By.xpath("//*[@id=\"f-Investment Trusts\"]")).isSelected();
			 driver.findElement(By.xpath("//*[@id=\"f-Investment Trusts\"]")).click();
			 System.out.print(currentURL);
			 driver.findElement(By.xpath("//*[@id=\"content\"]/div[2]/div/div[1]/div[2]/div[1]/div/input")).getLocation();
			 driver.findElement(By.xpath("//*[@id=\"content\"]/div[2]/div/div[1]/div[2]/div[1]/div/input")).sendKeys("LU0210527791");
			 driver.findElement(By.xpath("//*[@id=\"content\"]/div[2]/div/div[1]/div[2]/div[1]/div/a/i")).click();
			 Thread.sleep(5000);
			  driver.findElement(By.xpath("//td[@class='ng-scope dotdotdot']//*[@class='ng-binding']")).click();
	             driver.findElement(By.id("PerformanceLi")).click();
			 
			 
			
			 

		} catch (Exception e) {
			e.printStackTrace();
			
		}
		
	}
		
		

		


	public static void main(String[] args) {
		
       Day1 myObj =new Day1();
       myObj.invokeBrowser(myObj, myObj,  myObj);
       
 
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

