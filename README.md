Feature: Salesforce API Automation for Opportunity

  Background:
    Given We have loaded "API" properties file

  @TC_01_Generate_Access_Token
  Scenario: Generate Salesforce Access Token
    Given I set token URL to "https://test.salesforce.com/services/oauth2/token"
    And I prepare token request with grant_type "password"
    And I add token field "username" as "atfdigitalintegration@barclays.com"
    And I add token field "password" as "Barclays12345@@"
    And I add token field "client_id" as "<your-client-id>"
    And I add token field "client_secret" as "<your-client-secret>"
    When I send token request using POST method
    Then I store the access token for future use

  @TC_02_Create_Opportunity
  Scenario: Create Opportunity using Salesforce API
    Given I set API endpoint to "https://buk-b2b-amidev.sandbox.my.salesforce.com/services/apexrest/OMLDigitalOpportunity"
    And I prepare Opportunity request body with "ATF Digital Opportunity1"
    And I add header "Content-Type" equals "application/json"
    And I add header "Authorization" equals "Bearer <access_token>"
    When I send REST API request using "POST" method
    Then I validate API response status code is 200
    And I extract Opportunity ID from response

  @TC_03_Verify_Opportunity_in_Salesforce
  Scenario: Verify created Opportunity in Salesforce UI
    Given I open Salesforce global search
    When I search for Opportunity by name "ATF Digital Opportunity1"
    Then I should see Opportunity visible in search results
