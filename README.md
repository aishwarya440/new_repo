// Cast driver to JavaScriptExecutor
JavascriptExecutor js = (JavascriptExecutor) driver;

// 1. Get the shadow host (the lightning component)
WebElement shadowHost = driver.findElement(By.cssSelector("lightning-accordion-section"));

// 2. Access shadow root
WebElement shadowRoot = (WebElement) js.executeScript("return arguments[0].shadowRoot", shadowHost);

// 3. Get the <slot> inside shadow DOM
WebElement slot = shadowRoot.findElement(By.cssSelector("slot"));

// 4. Get assigned text from <slot>
String text = (String) js.executeScript("return arguments[0].assignedNodes()[0].textContent.trim()", slot);

System.out.println("Text from slot: " + text);
