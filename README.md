@And("I verify below elements on {string} screen")
public void verify_multiple_elements_on_screen(String screenName, DataTable dataTable) {
    List<String> elementList = dataTable.asList();

    for (String elementName : elementList) {
        try {
            boolean isDisplayed = genIsDisplayedWebElement(elementName, screenName);

            if (isDisplayed) {
                logger.info("Element {} on {} is displayed", elementName, screenName);
                htmlReporterWebClassInstance.reportStep(
                        "<b>" + screenName + ":</b> Element " + elementName + " exists",
                        "Element " + elementName + " exists on " + screenName + " screen and is verified successfully",
                        true, true);
            } else {
                logger.warn("Element {} on {} is not displayed", elementName, screenName);
                htmlReporterWebClassInstance.reportStep(
                        "<b>" + screenName + ":</b> Element missing",
                        "Element " + elementName + " does not exist on " + screenName + " screen",
                        false, true);
            }
        } catch (Exception e) {
            Exceptions.otherException(e.toString(), screenName);
        }
    }
}
