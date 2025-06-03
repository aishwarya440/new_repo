List<String> tabNames = slotItems.stream()
        .map(slot -> (String) js.executeScript("return arguments[0].assignedNodes()[0].textContent.trim()", slot))
        .collect(Collectors.toList());

    // 5. Return the result
    return tabNames;
