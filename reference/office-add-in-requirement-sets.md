
# Office add-in requirement sets

Requirement sets are named groups of API members. Office Add-ins use requirement sets specified in the manifest or using a runtime check to determine if an Office host supports APIs needed by the add-in. For more information, see [Specify Office hosts and API requirements](../docs/overview/specify-office-hosts-and-api-requirements.md).

To get a broad view of where add-ins are supported by Office host, see the [Office Add-in host and platform availability](https://dev.office.com/add-in-availability) page.

## Requirement sets


The following table lists the names of requirement sets, the methods in each set, the Office host applications that support that requirement set, and the version number of the API.

For information about requirement sets for Outlook, see [Understanding Outlook API requirement sets](./outlook/tutorial-api-requirement-sets.md).

|**Set name**|**Version**|**Office host**|**Methods in set**|
|:-----|:-----|:-----|:-----|
|ExcelApi|1.2|Excel 2016<br>Excel&nbsp;Online<br>Excel for iPad<br>|Worksheet Protection<br>Worksheet Functions<br>Sort<br>Filter<br>R1C1 Reference Style<br>Merge Cells<br>Adjust Row Height and Column Width<br>Chart.getImage()<br>Range.getUsedRange(valuesOnly)|
|ExcelApi|1.1|Excel 2016<br>Excel&nbsp;Online<br>Excel for iPad<br>|All elements in the Excel namespace|
|WordApi|1.2|Word 2016<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word for iPad<br>|All elements in the Word namespace. The following methods were added to this version of WordApi:<br>Body.select(selectionMode)<br>Body.insertInlinePictureFromBase64(base64EncodedImage, insertLocation)<br>contentControl.select(selectionMode)<br>contentControl.insertInlinePictureFromBase64(base64EncodedImage, insertLocation)<br>inlinePicture.paragraph<br>inlinePicture.delete<br>inlinePicture.insertBreak(breakType, insertLocation)<br>inlinePicture.insertFileFromBase64(base64file, insertLocation)<br>inlinePicture.insertHtml(html, insertLocation)<br>inlinePicture.insertInlinePictureFromBase64(base64file, insertLocation)<br>inlinePicture.insertOoxml(ooxml, insertLocation)<br>inlinePicture.insertParagraph(paragraphText, insertLocation)<br>inlinePicture.insertText(text, insertLocation)<br>inlinePicture.select(selectionMode)<br>paragraph.select(selectionMode)<br>range.inlinePictures<br>range.select(selectionMode)<br>range.insertInlinePictureFomBase64(base64EcodedImage, insertLocation)|
|WordApi|1.1|Word 2016<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word for iPad<br>|All elements in the Word namespace except API members that were added to WordApi 1.2 and later, which are listed above.|
|ActiveView|1.1|PowerPoint<br>PowerPoint&nbsp;Online|Document.getActiveViewAsync|
|BindingEvents|1.1|Access&nbsp;Web&nbsp;Apps<br>Excel<br>Excel&nbsp;Online<br>Word&nbsp;2013&nbsp;and&nbsp;later<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word&nbsp;Online<br>Word&nbsp;for&nbsp;iPad|Binding.addHanderAsync<br>Binding.removeHanderAsync|
|CompressedFile|1.1|PowerPoint<br>Word&nbsp;2013&nbsp;and&nbsp;later<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word&nbsp;Online<br>Word&nbsp;for&nbsp;iPad<br/>Excel&nbsp;Online<br/>PowerPoint&nbsp;Online|Supports output to Office Open XML (OOXML) format as a byte array<br>(Office.FileType.Compressed) when using the Document.getFileAsync method.|
|CustomXmlParts|1.1|Word&nbsp;2013&nbsp;and&nbsp;later<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word&nbsp;Online<br>Word&nbsp;for&nbsp;iPad|CustomXmlNode.getNodesAsync<br>CustomXmlNode.getNodeValueAsync<br>CustomXmlNode.getXmlAsync<br>CustomXmlNode.setNodeValueAsync<br>CustomXmlNode.setXmlAsync<br>CustomXmlPart.addHandlerAsync<br>CustomXmlPart.deleteAsync<br>CustomXmlPart.getNodesAsync<br>CustomXmlPart.getXmlAsync<br>CustomXmlPart.removeHandlerAsync<br>CustomXmlParts.addAsync<br>CustomXmlParts.getByIdAsync<br>CustomXmlParts.getByNamespaceAsync<br>CustomXmlPrefixMappings.addNamespaceAsync<br>CustomXmlPrefixMappings.getNamespaceAsync<br>CustomXmlPrefixMappings.getPrefixAsync|
|DialogAPI|1.1|Excel<br>PowerPoint<br>Word 2016<br>Outlook|Office.context.ui.displayDialogAsync()<br>Office.context.ui.messageParent()<br>Office.context.ui.close()|
|DocumentEvents|1.1|Excel<br>Excel&nbsp;Online<br>PowerPoint<br>Word&nbsp;2013&nbsp;and&nbsp;later<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word&nbsp;Online<br>Word&nbsp;for&nbsp;iPad|Document.addHandlerAsync<br>Document.removeHandlerAsync|
|File|1.1|PowerPoint<br>Word&nbsp;2013&nbsp;and&nbsp;later<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word&nbsp;Online<br>Word&nbsp;for&nbsp;iPad<br>PowerPoint&nbsp;Online|Document.getFileAsync<br>File.closeAsync<br>File.getSliceAsync|
|HtmlCoercion|1.1|Word&nbsp;2013&nbsp;and&nbsp;later<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word&nbsp;Online<br>Word&nbsp;for&nbsp;iPad|Supports coercion to HTML (Office.CoercionType.Html) when reading and writing data using the Document.getSelectedDataAsync,<br>Document.setSelectedDataAsync, Binding.getDataAsync, or Binding.setDataAsync methods.|
|ImageCoercion|1.1|Word&nbsp;2013&nbsp;and&nbsp;later<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word&nbsp;Online<br>Word&nbsp;for&nbsp;iPad|Supports conversion to an image (Office.CoercionType.Image) when writing data using the Document.setSelectedDataAsync method.|
|Mailbox||Outlook for Windows<br>Outlook for web<br>Outlook for Mac<br>Outlook Web App |see [Understanding Outlook API requirement sets](./outlook/tutorial-api-requirement-sets.md)|
|MatrixBindings|1.1|Excel<br>Excel&nbsp;Online<br>Word|Bindings.addFromNamedItemAsync<br>Bindings.addFromSelectionAsync<br>Bindings.getAllAsync<br>Bindings.getByIdAsync<br>Bindings.releaseByIdAsyncMatrix<br>Binding.getDataAsyncMatrix<br>Binding.setDataAsync|
|MatrixCoercion|1.1|Excel<br>Excel&nbsp;Online<br>Word&nbsp;2013&nbsp;and&nbsp;later<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word&nbsp;Online<br>Word&nbsp;for&nbsp;iPad|Supports coercion to the "matrix" (array of arrays) data structure (Office.CoercionType.Matrix) when reading and writing data using the Document.getSelectedDataAsync, Document.setSelectedDataAsync, Binding.getDataAsync, or Binding.setDataAsync methods.|
|OoxmlCoercion|1.1|Word&nbsp;2013&nbsp;and&nbsp;later<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word&nbsp;Online<br>Word&nbsp;for&nbsp;iPad|Supports coercion to Open Office XML (OOXML) format (Office.CoercionType.Ooxml) when reading and writing data using the Document.getSelectedDataAsync, Document.setSelectedDataAsync, Binding.getDataAsync, or Binding.setDataAsync methods.|
|PartialTableBindings|1.1|Access&nbsp;Web&nbsp;Apps||
|PdfFile|1.1|PowerPoint<br/>PowerPoint&nbsp;Online<br/>Word&nbsp;2013&nbsp;and&nbsp;later<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word&nbsp;Online<br>Word&nbsp;for&nbsp;iPad|Supports output to PDF format (Office.FileType.Pdf)<br>when using the Document.getFileAsync method.|
|Selection|1.1|Excel<br>Excel&nbsp;Online<br>PowerPoint<br>Project<br>Word&nbsp;2013&nbsp;and&nbsp;later<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word&nbsp;Online<br>Word&nbsp;for&nbsp;iPad|Document.getSelectedDataAsync<br>Document.setSelectedDataAsync|
|Settings|1.1|Access&nbsp;Web&nbsp;Apps<br>Excel<br>Excel&nbsp;Online<br>PowerPoint<br>PowerPoint&nbsp;Online<br>Word&nbsp;2013&nbsp;and&nbsp;later<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word&nbsp;Online<br>Word&nbsp;for&nbsp;iPad|Settings.get<br>Settings.remove<br>Settings.saveAsync<br>Settings.set|
|TableBindings|1.1|Access&nbsp;Web&nbsp;Apps<br>Excel<br>Excel&nbsp;Online<br>Word&nbsp;2013&nbsp;and&nbsp;later<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word&nbsp;Online<br>Word&nbsp;for&nbsp;iPad|Bindings.addFromNamedItemAsync<br>Bindings.addFromSelectionAsync<br>Bindings.getAllAsync<br>Bindings.getByIdAsync<br>Bindings.releaseByIdAsyncTable<br>Binding.addColumnsAsyncTable<br>Binding.addRowsAsyncTable<br>Binding.deleteAllDataValuesAsyncTable<br>Binding.getDataAsyncTable<br>Binding.setDataAsync|
|TableCoercion|1.1|Access&nbsp;Web&nbsp;Apps<br>Excel<br>Excel&nbsp;Online<br>Word&nbsp;2013&nbsp;and&nbsp;later<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word&nbsp;Online<br>Word&nbsp;for&nbsp;iPad|Supports coercion to the "table" data structure (Office.CoercionType.Table) when reading and writing data using the Document.getSelectedDataAsync, Document.setSelectedDataAsync, Binding.getDataAsync, or Binding.setDataAsync methods.|
|TextBindings|1.1|Excel<br>Excel&nbsp;Online<br>Word&nbsp;2013&nbsp;and&nbsp;later<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word&nbsp;Online<br>Word&nbsp;for&nbsp;iPad|Bindings.addFromNamedItemAsync<br>Bindings.addFromSelectionAsync<br>Bindings.getAllAsync<br>Bindings.getByIdAsync<br>Bindings.releaseByIdAsyncText<br>Binding.getDataAsyncText<br>Binding.setDataAsync|
|TextCoercion|1.1|Excel<br>Excel&nbsp;Online<br>PowerPoint<br>Project<br>Word&nbsp;2013&nbsp;and&nbsp;later<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word&nbsp;Online<br>Word&nbsp;for&nbsp;iPad|Supports coercion to text format (Office.CoercionType.Text) when reading and writing data using the Document.getSelectedDataAsync, Document.setSelectedDataAsync, Binding.getDataAsync, or Binding.setDataAsync methods.|
|TextFile|1.1|Word&nbsp;2013&nbsp;and&nbsp;later<br>Word&nbsp;2016&nbsp;for&nbsp;Mac<br>Word&nbsp;Online<br>Word&nbsp;for&nbsp;iPad<br/>|Supports output to text format (Office.FileType.Text) when using the Document.getFileAsync method.|

## Methods that aren't part of a requirement set


The following methods in the JavaScript API for Office aren't part of a requirement set. If your add-in requires any of these methods, use the  **Methods** and **Method** elements in the add-in's manifest to declare that they are required, or perform the runtime check using an if statement. For more information, see [Specify Office hosts and API requirements](../docs/overview/specify-office-hosts-and-api-requirements.md).



|**Method name**|**Office host support**|
|:-----|:-----|
|Bindings.addFromPromptAsync|Access web apps, Excel, and Excel Online|
|Document.getFilePropertiesAsync|Excel, Excel Online, Word, and PowerPoint|
|Document.getProjectFieldAsync|Project Standard 2013 and Project Professional 2013|
|Document.getResourceFieldAsync|Project Standard 2013 and Project Professional 2013|
|Document.getSelectedResourceAsync|Project Standard 2013 and Project Professional 2013|
|Document.getSelectedTaskAsync|Project Standard 2013 and Project Professional 2013|
|Document.getSelectedViewAsync|PowerPoint and PowerPoint Online|
|Document.getTaskAsync|Project Standard 2013 and Project Professional 2013|
|Document.getTaskFieldAsync|Project Standard 2013 and Project Professional 2013|
|Document.goToByIdAsync|Excel, Excel Online, Word, and PowerPoint|
|Settings.addHandlerAsync|Access web apps, Excel, Excel Online, Word, and PowerPoint|
|Settings.refreshAsync|Access web apps, Excel, Excel Online, Word, PowerPoint, and PowerPoint Online|
|Settings.removeHandlerAsync|Access web apps, Excel, Excel Online, Word, and PowerPoint|
|TableBinding.clearFormatsAsync|Excel, Excel Online|
|TableBinding.setFormatsAsync|Excel, Excel Online|
|TableBinding.setTableOptionsAsync|Excel, Excel Online|

## Additional resources



- [Specify Office hosts and API requirements](../docs/overview/specify-office-hosts-and-api-requirements.md)

