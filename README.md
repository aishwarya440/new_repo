JavascriptExecutor js = (JavascriptExecutor) driver;

WebElement shadowHost = driver.findElement(By.cssSelector("lightning-accordion-section"));
SearchContext shadowRoot = (SearchContext) js.executeScript("return arguments[0].shadowRoot", shadowHost);

// Then find the <slot> inside shadowRoot
List<WebElement> slotItems = shadowRoot.findElements(By.cssSelector("slot"));

for (WebElement slot : slotItems) {
    String text = (String) js.executeScript("return arguments[0].assignedNodes()[0].textContent.trim()", slot);
    System.out.println("Tab: " + text);
}
