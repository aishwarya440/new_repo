
JavascriptExecutor js = (JavascriptExecutor) driver;

String slotText = (String) js.executeScript(
    "let slot = arguments[0].shadowRoot.querySelector('slot');" +
    "return Array.from(slot.assignedNodes())" +
    "  .filter(n => n.nodeType === Node.TEXT_NODE)" + // Only text
    "  .map(n => n.textContent.trim())" +
    "  .join(', ');",
    shadowHost
);

System.out.println("Slot text: " + slotText);
