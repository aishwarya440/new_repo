System.out.println("SCREEN RAW: [" + textOnScreen + "]");
System.out.println("SCREEN HEX : " + toHex(textOnScreen));

private String toHex(String value) {
    StringBuilder sb = new StringBuilder();
    for (char c : value.toCharArray()) {
        sb.append(String.format("\\u%04X", (int) c));
    }
    return sb.toString();
}
