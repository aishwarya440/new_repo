TC01 – Verify new parameters (expAnnualExpenditure, expAnnualTurnover, atfOmFlag) appear in Assisted Decision payload
TC02 – Validate expAnnualExpenditure value flows correctly into API request
TC03 – Validate expAnnualTurnover value flows correctly into API request
TC04 – Validate atfOmFlag mapping and format (A–Z only, max 5 chars)
TC05 – Verify system rejects invalid atfOmFlag values
TC06 – Verify blank/null values for new parameters are handled correctly
TC07 – Verify Assisted Decision response is successful after adding new fields (no regression)
TC08 – Verify error handling when new parameter value causes callout failure
