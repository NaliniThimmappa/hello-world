package selenium;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;

import com.sun.xml.internal.bind.v2.schemagen.xmlschema.List;

public class nal {

	public static void main(String[] args) throws InterruptedException {
		// TODO Auto-generated method stub
		System.setProperty("webdriver.chrome.driver", "C:\\SELENIUM\\Drivers\\chromedriver.exe");
		WebDriver driver= new ChromeDriver();
		/*//WebDriver driver= new FirefoxDriver();*/
		driver.get("https://www.allahabadbank.in/english/emi_calculator.aspx");
		driver.manage().window().maximize();
		driver.findElement(By.name("principal")).sendKeys("4000");
		driver.findElement(By.name("interest")).sendKeys("2");
		driver.findElement(By.id("three")).sendKeys("12");
		driver.findElement(By.name("B1")).click();
		/*List<WebElement> listElement= driver.findElement(By.name("total")).getText();
		for(int i=0;i=listElement;i++)
		{
			String ElementText= listElement.get(i).getText();
			System.out.println(ElementText);
		}*/
		driver.wait(3000);
		driver.close();
	}
}
