
String slotText = (String) js.executeScript(
    "const slot = arguments[0];" +
    "if (!slot) return '';" +
    "return Array.from(slot.assignedNodes())" +
    ".map(n => n.textContent.trim())" +
    ".filter(Boolean)" +
    ".join('\\n');",
    securityTabs
);
