---
title: Export to Image
page_title: Export to Image | UI for ASP.NET AJAX Documentation
description: Export to Image
slug: diagram/import-and-export/export-to-image
tags: export,to,image
published: True
position: 1
---

# Export to Image



## 

You can export __RadDiagram__ as an image on the client. This is done in two simple steps (__Example 1__):

1. Get a reference to the client-side object of the underlying Kendo UI diagram as described in the [Overview]({%slug diagram/client-side-programming/overview%}) help article.

1. Call the[exportImage](http://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/diagram#methods-exportImage) method of the client-side object of the diagram.

>caution The export to image functionality is currently supported in Firefox, Chrome, IE10+ and Opera 15.0+ (Blink).
>


__Example 1__: Export a diagram as an image.

````ASPNET
	    <telerik:RadDiagram ID="RadDiagram1" runat="server">
	        <LayoutSettings Type="Tree" Subtype="Down" Enabled="true">
	        </LayoutSettings>
	        <ClientEvents OnLoad="onLoad" />
	        <ShapesCollection>
	            <telerik:DiagramShape Id="DiagramShape1"></telerik:DiagramShape>
	            <telerik:DiagramShape Id="DiagramShape2"></telerik:DiagramShape>
	        </ShapesCollection>
	        <ConnectionsCollection>
	            <telerik:DiagramConnection>
	                <FromSettings Connector="Top" ShapeId="DiagramShape1" />
	                <ToSettings Connector="Bottom" ShapeId="DiagramShape2" />
	                <StrokeSettings />
	            </telerik:DiagramConnection>
	        </ConnectionsCollection>
	    </telerik:RadDiagram>
	    <script type="text/javascript">
	        function onLoad(diagram) {
	            var diagramWidget = diagram.get_kendoWidget();
	            diagramWidget.exportImage().done(function (data) {
	                kendo.saveAs({
	                    dataURI: data,
	                    fileName: "diagram.png"
	                });
	            });
	        }
	    </script>
````



You can find a list of the available parameters of the __exportImage__ method in the [Kendo UI Diagram API Reference](http://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/diagram#methods-exportImage).

# See Also

 * [RadDiagram Client-Side Basics]({%slug diagram/client-side-programming/overview%})

 * [exportImage method of Kendo UI Diagram](http://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/diagram#methods-exportImage)