# Kurtosys
Test
Functional UI Test ( Imanage to teach myself selenium over 2 days and i got stuck with the code and only manage to get this done 
---
package co.edureka.selenium.webdriver.basic;

import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class Day1 {

	WebDriver driver;
	JavascriptExecutor jse;
	
	public void invokeBrowser() {
		
		try {
			System.setProperty("webdriver.chrome.driver", "C:\\Users\\joshua.kinnear\\Desktop\\Test\\chromedriver.exe");
			driver = new ChromeDriver();
			driver.manage().deleteAllCookies();
			driver.manage().window().maximize();
			driver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
			driver.manage().timeouts().pageLoadTimeout(30, TimeUnit.SECONDS);
			
			driver.get("https://am.jpmorgan.com/gb/en/asset-management/gim/adv/home");
			inputName();
			inputClick();
		} catch (Exception e) {
			e.printStackTrace();
		}
		
}
	
	public void inputClick() {
	  driver.findElement(By.name("Accept the disclaimer")).click();
	  jse = (JavascriptExecutor)driver;
	  jse.executeScript("scroll(0, 1000)");
	  
	 
	}
	public void inputName() {
	 driver.findElement(By.id("ng-app"));
	 driver.findElement(By.className("icon-rightchevron")).click();
	  jse = (JavascriptExecutor)driver;
	  jse.executeScript("scroll(0, 1000)");
	  
	 
	}


	public static void main(String[] args) {
		
       Day1 myObj =new Day1();
       myObj.invokeBrowser();
       
       
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

