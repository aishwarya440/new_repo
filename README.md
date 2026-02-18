Sub ListSheetsWithLinks()

    Dim ws As Worksheet
    Dim i As Integer
    
    i = 1
    Sheets("TestCases").Columns(1).ClearContents
    
    For Each ws In ThisWorkbook.Worksheets
        Sheets("TestCases").Hyperlinks.Add _
        Anchor:=Sheets("TestCases").Cells(i, 1), _
        Address:="", _
        SubAddress:="'" & ws.Name & "'!A1", _
        TextToDisplay:=ws.Name
        
        i = i + 1
    Next ws

End Sub
