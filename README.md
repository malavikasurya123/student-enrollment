import org.openqa.selenium.Alert;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class StudentEnrollmentPageTest {
    public static void main(String[] args) {

        // Set the path to the ChromeDriver executable
        System.setProperty("webdriver.chrome.driver", "PATH_TO_CHROMEDRIVER");

        // Launch Chrome Browser
        WebDriver driver = new ChromeDriver();

        // Navigate to the Student Enrollment page
        driver.get("https://qastdenroll.ccbp.tech/");

        // Enter the text "John" in the name input field
        WebElement nameInputField = driver.findElement(By.id("name"));
        nameInputField.sendKeys("John");

        // Click the "Enroll" button
        WebElement enrollButton = driver.findElement(By.className("submit-button"));
        enrollButton.click();

        // Declare the Alert object
        Alert alertObj = driver.switchTo().alert();

        // Print the text content of the alert
        System.out.println(alertObj.getText());

        // Accept the alert
        alertObj.accept();

        // Enter the text "John@gmail.com" in the email input field
        WebElement emailInputField = driver.findElement(By.id("email"));
        emailInputField.sendKeys("john@gmail.com");

        // Click the "Enroll" button
        enrollButton.click();

        // Print the text content of the alert
        System.out.println(alertObj.getText());

        // Accept the alert
        alertObj.accept();

        // Quit the WebDriver instance
        driver.quit();
    }
}
