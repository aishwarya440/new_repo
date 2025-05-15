@And("I verify all sections are disabled under {string} tab for process type {string}")
public void i_verify_all_sections_disabled_under_tab(String tabName, String processType) 
        throws XMLStreamException, FileNotFoundException {

    // Click on the Security tab
    pswStepDefinitionHelperWebClassInstance.clickOnElementOnScreen(field: tabName, screenName: "ProcessInfoTab");

    // List of section field names under the Security tab (adjust based on actual identifiers in your system)
    List<String> sectionFields = Arrays.asList(
        "securityDetailsSection",
        "partyDetailsSection",
        "guaranteeDetailsSection",
        "signerDetailsSection",
        "companyOutcomesSection"
    );

    for (String section : sectionFields) {
        pswStepDefinitionHelperWebClassInstance.genIsEnabledWebElement(field: section, action: "disabled", screenName: tabName);
        logger.info(section + " is verified as readonly under tab: " + tabName + " for process: " + processType);
    }
}
