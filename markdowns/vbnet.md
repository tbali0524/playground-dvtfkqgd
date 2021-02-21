# VB.NET

## Checking the sample code

```vb.net runnable
Module Solution

    Function DecimalToBinary(dec As Integer) As String
        If dec < 1 Then Return "0"
        Dim binStr As String = String.Empty
        While dec > 0
            binStr = binStr.Insert(0, (dec Mod 2).ToString())
            dec = Int(dec / 2)
        End While
        Return binStr
    End Function

    Sub Main ()
        Dim m as String
        'm = Console.ReadLine()
        m = "CG"
        Dim c(2) as String
        c(0) = "00"
        c(1) = "0"
        Dim b = ""
        For Each ch As Char in m
            b = b & DecimalToBinary(Asc(ch)).PadLeft(7, "0")
        Next
        Dim a = c(Asc(b.Chars(0)) - Asc("0")) & " 0"
        for i as Integer = 1 To b.Length() - 1
            if (b(i) = b(i - 1)) then
                a = a & "0"
            else
                a = a & " " & c(Asc(b.Chars(i)) - Asc("0")) & " 0"
            end if
        next
        ' Console.Error.WriteLine("Debug messages...")
        Console.WriteLine(a)
    End Sub
End Module
```

## Looking at the syntax

- TODO

## Other characteristics

- TODO

## Resources to check

- [Overview on Wikipedia](https://en.wikipedia.org/wiki/Visual_Basic_.NET)
- [Official documentation](https://docs.microsoft.com/hu-hu/dotnet/visual-basic/)
