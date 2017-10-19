

package selenium;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;

public class nal3 {

	public static void main(String[] args) throws InterruptedException {
		// TODO Auto-generated method stub
			System.setProperty("webdriver.chrome.driver", "C:\\SELENIUM\\Drivers\\chromedriver.exe");
			WebDriver driver = new ChromeDriver();
			driver.get("https://www.allahabadbank.in/english/emi_calculator.aspx");
			WebDriver driver1 = new FirefoxDriver();
			driver1.get("https://www.google.com");
			driver1.findElement(By.className("gb_P")).click();
		//	String text = driver1.findElement(By.className("gb_P")).getText();
		//	System.out.println(text);
		/*	driver.close();
			//driver1.close();*/
			driver1.quit();
	}

}
