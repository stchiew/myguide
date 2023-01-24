# OpenXML samples

Using PowerTools module

```
# Import the Open-Xml-PowerTools module
Import-Module Open-Xml-PowerTools

# Open the document
$wordDoc = (Get-Content -Path "path\to\document.docx" -Encoding Byte)

# Replace the paragraph at the specified index with the new text
$wordDoc = Replace-OpenXmlElement -Path $wordDoc -ElementName "w:p" -Index $index -Text $text

# Save the modified document
$wordDoc | Set-Content -Path "path\to\modified_document.docx" -Encoding Byte
```

C# code

```
using (WordprocessingDocument doc = WordprocessingDocument.Open(fileName, true))
{
    MainDocumentPart mainPart = doc.MainDocumentPart;
    Paragraph p = mainPart.Document.Body.Elements<Paragraph>().ElementAt(index);
    p.Remove();
    Paragraph newP = new Paragraph(new Run(new Text(text)));
    mainPart.Document.Body.InsertAt(newP, index);
    mainPart.Document.Save();
}
```

Suggested by chatgpt

```
$mainPart = $doc.MainDocumentPart
$p = $mainPart.Document.Body.Elements<Paragraph>().ElementAt($index)
$p.Remove()
$newP = New-Object -TypeName Microsoft.OpenXml.Wordprocessing.Paragraph -ArgumentList (New-Object -TypeName Microsoft.OpenXml.Wordprocessing.Run -ArgumentList (New-Object -TypeName Microsoft.OpenXml.Wordprocessing.Text -ArgumentList $text))
$mainPart.Document.Body.InsertAt($newP, $index)
$mainPart.Document.Save()
```
