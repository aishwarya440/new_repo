Feature: Generate Salesforce Access Token via API

  Background:
    Given We have loaded "API" properties file

  @TC_01_Generate_Token_From_Image
  Scenario: Generate Access Token from Salesforce using Password Grant
    Given I set the token URL to "https://test.salesforce.com/services/oauth2/token"
    And I set form parameter "username" to "atfdigitalintegration@barclays.com"
    And I set form parameter "password" to "Barclays12345@@"
    And I set form parameter "client_id" to "3MVG98JTgk_v4c1ErF2WKu..."
    And I set form parameter "client_secret" to "A350F0F4F3ECDC6219C806..."
    And I set form parameter "grant_type" to "password"
    When I send the POST request to get the token
    Then I should receive a 200 OK response
    And I store the "access_token" value
    And I print the token for debugging



  package stepDefinitions;

import io.cucumber.java.en.*;
import io.restassured.RestAssured;
import io.restassured.response.Response;
import org.junit.Assert;

import java.util.HashMap;
import java.util.Map;

public class TokenStepDefs {

    private String tokenUrl;
    private Map<String, String> formParams = new HashMap<>();
    private Response response;

    @Given("I set the token URL to {string}")
    public void i_set_the_token_url(String url) {
        this.tokenUrl = url;
    }

    @And("I set form parameter {string} to {string}")
    public void i_set_form_parameter(String key, String value) {
        formParams.put(key, value);
    }

    @When("I send the POST request to get the token")
    public void i_send_post_request_to_get_token() {
        response = RestAssured
            .given()
            .formParams(formParams)
            .post(tokenUrl);
    }

    @Then("I should receive a {int} OK response")
    public void i_should_receive_a_ok_response(int statusCode) {
        Assert.assertEquals(statusCode, response.getStatusCode());
    }

    @And("I store the {string} value")
    public void i_store_the_token_value(String key) {
        String token = response.jsonPath().getString(key);
        TokenManager.setToken(token);
    }

    @And("I print the token for debugging")
    public void i_print_the_token() {
        System.out.println("Access Token: " + TokenManager.getToken());
    }
}




package utilities;

public class TokenManager {

    private static String accessToken;

    public static void setToken(String token) {
        accessToken = token;
    }

    public static String getToken() {
        return accessToken;
    }
}
