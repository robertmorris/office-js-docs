# Section Object (JavaScript API for OneNote)

_Applies to: OneNote Online_
_Note: This API is in preview_

Represents a OneNote section. Sections can contain pages.

## Properties

| Property	   | Type	|Description
|:---------------|:--------|:----------|
|id|string|Gets the ID of the section. Read-only.|
|name|string|Gets the name of the section. Read-only.|

_See property access [examples.](#property-access-examples)_

## Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|notebook|[Notebook](notebook.md)|Gets the notebook that contains the section. Read-only.|
|sectionGroup|[SectionGroup](sectiongroup.md)|Gets the section group that contains the section. Returns null if the section is a direct child of the notebook. Read-only.|

## Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[addPage(title: string)](#addpagetitle-string)|[Page](page.md)|Adds a new page to the end of the section.|
|[getPages()](#getpages)|[PageCollection](pagecollection.md)|Gets the collection of pages in the section.|
|[insertSectionAsSibling(location: string, title: string)](#insertsectionassiblinglocation-string-title-string)|[Section](section.md)|Inserts a new section before or after the current section.|
|[load(param: object)](#loadparam-object)|void|Fills the proxy object created in JavaScript layer with property and object values specified in the parameter.|

## Method Details


### addPage(title: string)
Adds a new page to the end of the section.

#### Syntax
```js
sectionObject.addPage(title);
```

#### Parameters
| Parameter	   | Type	|Description|
|:---------------|:--------|:----------|
|title|string|The title of the new page.|

#### Returns
[Page](page.md)

#### Examples
```js
OneNote.run(function (context) {
            
    // Queue a command to add a page to the current section.
    var page = context.application.activeSection.addPage("Wish list");
            
    // Queue a command to load the id and title of the new page. 
    // This example loads the new page so it can read its properties later.           
    page.load('id,title');
            
    // Run the queued commands, and return a promise to indicate task completion.
    return context.sync()
        .then(function () {
             
            // Display the properties.       
            console.log("Page name: " + page.title);
            console.log("Page ID: " + page.id);

        });
    })
    .catch(function(error) {
        console.log("Error: " + error);
        if (error instanceof OfficeExtension.Error) {
            console.log("Debug info: " + JSON.stringify(error.debugInfo));
        }
    });
```


### getPages()
Gets the collection of pages in the section.

#### Syntax
```js
sectionObject.getPages();
```

#### Parameters
None

#### Returns
[PageCollection](pagecollection.md)

#### Examples
```js
OneNote.run(function (context) {
            
    // Get the pages in the current section.
    var pages = context.application.activeSection.getPages();
            
    // Queue a command to load the id and title for each page.            
    pages.load('id,title');
            
    // Run the queued commands, and return a promise to indicate task completion.
    return context.sync()
        .then(function () {
            
            // Display the properties.         
            $.each(pages.items, function(index, page) {
                console.log("Page name: " + page.title);
                console.log("Page ID: " + page.id);
            });
        });
    })
    .catch(function(error) {
        console.log("Error: " + error);
        if (error instanceof OfficeExtension.Error) {
            console.log("Debug info: " + JSON.stringify(error.debugInfo));
        }
    });
```


### insertSectionAsSibling(location: string, title: string)
Inserts a new section before or after the current section.

#### Syntax
```js
sectionObject.insertSectionAsSibling(location, title);
```

#### Parameters
| Parameter	   | Type	|Description|
|:---------------|:--------|:----------|
|location|string|The location of the new section relative to the current section.  Possible values are: Before, After|
|title|string|The name of the new section.|

#### Returns
[Section](section.md)

#### Examples
```js
OneNote.run(function (context) {
            
    // Queue a command to insert a section after the current section.
    var section = context.application.activeSection.insertSectionAsSibling("After", "New section");
            
    // Queue a command to load the id and name of the new section. 
    // This example loads the new section so it can read its properties later.           
    section.load('id,name');
            
    // Run the queued commands, and return a promise to indicate task completion.
    return context.sync()
        .then(function () {
             
            // Display the properties.       
            console.log("Section name: " + section.name);
            console.log("Section ID: " + section.id);
        });
    })
    .catch(function(error) {
        console.log("Error: " + error);
        if (error instanceof OfficeExtension.Error) {
            console.log("Debug info: " + JSON.stringify(error.debugInfo));
        }
    });
```

### load(param: object)
Fills the proxy object created in JavaScript layer with property and object values specified in the parameter.

#### Syntax
```js
object.load(param);
```

#### Parameters
| Parameter	   | Type	|Description|
|:---------------|:--------|:----------|
|param|object|Optional. Accepts parameter and relationship names as delimited string or an array. Or, provide [loadOption](loadoption.md) object.|

#### Returns
void
### Property access examples

**id**
```js
OneNote.run(function (context) {
        
    // Get the current section.
    var section = context.application.activeSection;
            
    // Queue a command to load the section. 
    // For best performance, request specific properties.           
    section.load("id");
            
    // Run the queued commands, and return a promise to indicate task completion.
    return context.sync()
        .then(function () {
            console.log("Section ID: " + section.id);
        });
    })
    .catch(function(error) {
        console.log("Error: " + error);
        if (error instanceof OfficeExtension.Error) {
            console.log("Debug info: " + JSON.stringify(error.debugInfo));
        }
    });
```

**name and notebook**
```js
OneNote.run(function (context) {
        
    // Get the current section.
    var section = context.application.activeSection;
            
    // Queue a command to load the section with the specified properties. 
    section.load("name,notebook/name");
            
    // Run the queued commands, and return a promise to indicate task completion.
    return context.sync()
        .then(function () {
            console.log("Section name: " + section.name);
            console.log("Parent notebook name: " + section.notebook.name);
        });
    })
    .catch(function(error) {
        console.log("Error: " + error);
        if (error instanceof OfficeExtension.Error) {
            console.log("Debug info: " + JSON.stringify(error.debugInfo));
        }
    });
```


