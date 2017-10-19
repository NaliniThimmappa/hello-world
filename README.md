package selenium;

import java.io.BufferedReader;
import java.io.*;
import java.util.Scanner;
import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

import junit.framework.Assert;

public class nal2 {

/*	private static final TimeUnit SECONDS = null;
	private static final Boolean Boolean = null;*/

	public static void main(String[] args) throws InterruptedException {
		// TODO Auto-generated method stub
		//using scanner class
		System.setProperty("webdriver.chrome.driver", "C:\\SELENIUM\\Drivers\\chromedriver.exe");
		WebDriver driver = new ChromeDriver();
		driver.get("https://www.allahabadbank.in/english/emi_calculator.aspx");
		//driver.manage().window().maximize();
		driver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
        driver.manage().timeouts().pageLoadTimeout(120, TimeUnit.SECONDS);
		
		//input principal
		System.out.println("Enter the input string for Principal");
		Scanner scanner = new Scanner(System.in);
		String input = scanner.nextLine();	
		driver.findElement(By.name("principal")).sendKeys(input);

		
		//input rate of interest
		System.out.println("Please enter rate of interest:");
		Scanner scanner1 = new Scanner(System.in);
		String interest = scanner1.next();
		driver.findElement(By.name("interest")).sendKeys(interest);
		System.out.println("You entered interest:"+ interest);

		
		//input repayment
		System.out.println("Enter no of repayment");
		Scanner scanner2 = new Scanner(System.in);
		String repayment= scanner2.next();
		System.out.println("You entered:"+ repayment);
		driver.findElement(By.id("three")).sendKeys(repayment);
		
		//press submit
		driver.findElement(By.name("B1")).click();
		Thread.sleep(5000);
		String installment = driver.findElement(By.id("four")).getText();
		System.out.println("the payable installment is"+ installment);
		driver.quit();
		scanner.close();
		scanner1.close();
		scanner2.close();
	}

}
