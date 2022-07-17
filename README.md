# VBA-Multiple-lookup-Value
# VBA code to find all the lookup values as per the selected range
# Replica of XLOOKUP that can also give multiple values through lookup, concatenated by (,) and this can also be changed as per need
# After pasting this code, use function MULTILOOKUPN(Lookupvalue, Lookupvaluerange, Searchvaluerange)

Function MULTILOOKUPN(Lookupvalue As String, Lookupvaluerange As Range, Searchvaluerange As Range)
'1st Argument=Lookupvalue- The value that needs to be searched
'2nd Argument=Lookupvaluerange- The range that contains the value
'3rd Argument=Searchvaluerange- The range that contains the output values
Dim i As Long
For i = 1 To Lookupvaluerange.Rows.Count
If Lookupvaluerange.Cells(i, 1) = Lookupvalue Then
MULTILOOKUPN = MULTILOOKUPN & ", " & Searchvaluerange.Cells(i, 1)
End If
Next
MULTILOOKUPN = Right(MULTILOOKUPN, Len(MULTILOOKUPN) - 2)
End Function
