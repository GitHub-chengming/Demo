# Demo
用xpath元素定位连接火狐浏览器执行程序
package com.selenium.cn;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;

public class HelloWordWebdriver {
	

	public static void main(String agrs[]) throws Exception {
		
		System.setProperty("webdriver.bin", "C:/Program Files (x86)/Mozilla Firefox/firefox.exe");
		WebDriver driver = new FirefoxDriver();
		driver.get("http://baidu.com");

		WebElement query = driver.findElement(By.name("wd"));
		query.sendKeys("selenium 中文论坛");
		WebElement btn = driver.findElement(By.id("su"));
		btn.click();

		Thread.sleep(5000);

		WebElement link = driver.findElement(By.xpath("//*[@id='Search_button_globd']"));

		link.click();

		Thread.sleep(5000);

		driver.switchTo().window(
				driver.getWindowHandles().toArray(new String[0])[1]);

		System.out.println(driver.getTitle());

		driver.quit();
	}
}
