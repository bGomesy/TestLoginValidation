# TestLoginValidation
Validação de credenciais de acesso usando Selenium, WebDriver, JUnit e Cucumber e codificado em Java.



//Features MyApplication.feature
//feature: test login


//JUnit

Scenario: test login validation credentials

  Given Open chrome and start application
  When I enter valid username and valid password
  Then User should be able to login sucessfully


//criação de classe java
// nome da classe @testRun

package run;

import org.junit.run.RunWith;
import cucumber.api.junit.Cucumber;

@RunWith(Cucumber.class)
@Cucumber.Options(features ="features", glue = "Steps")


public class TestRun {

}

//novo pacote Steps
//nova classe @smokeTest


package step;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

import cucumber.api.java.en.Given;
import cucumber.api.java.en.Then;
import cucumber.api.java.en.When;

public class smokeTest
{

WebDriver driver;


@Given ("Open chrome and star application")
  public void Open_chrome_and_start_application() throws Throwable {

  driver - new ChromeDriver();
  driver.manager().window().maximize();
  driver.get("http://www.linkeind.com");

}


@When("I enter valid username and valid password")
  public void I_enter_valid_username_and_valid_password() thows Thowable {

  driver.findElement(By.id("email")).sendKeys("tomSmith@gmail.com");
  driver.findElement(By.id("pass")).sendKeys("SuperSecretPassword");

}

@Then("user should be able to login sucessfully")
  public void user_should_be_able_to_login_sucessfully() thows Thowable {
  driver.findElement(By.id("loginButton")).click();

  }
}
