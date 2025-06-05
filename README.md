Feature: Salesforce Opportunity API Automation

  Background:
    Given We have loaded "API" properties file

  @TC_01_Create_Opportunity
  Scenario: Create Opportunity using Salesforce API and validate
    Given I get Salesforce access token using password grant type
    And I set API endpoint to "https://buk-b2b-amidev.sandbox.my.salesforce.com/services/apexrest/OMLDigitalOpportunity"
    And I prepare Opportunity request body with "ATF Digital Opportunity1"
    And I add header "Content-Type" equals "application/json"
    And I add header "Authorization" equals "Bearer <token>"
    When I send REST API request using "POST" method
    Then I validate API response status code is 200
    And I validate Opportunity is created with name "ATF Digital Opportunity1"
