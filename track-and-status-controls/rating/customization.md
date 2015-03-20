---
title: Customization
page_title: Customization
description: Customization
slug: track-and-status-controls-rating-customization
tags: customization
published: True
position: 4
---

# Customization



## Hover, selected and selecting Background

__RadRating__ introduces an easy way to customize the item’s BackColor when hovering,
        selecting, selected a value:

#### __[C#]__

{{region Background}}
	            
	            foreach (RatingStarVisualElement item in this.radRating1.Items)
	            {
	                item.Fill.BackColor = Color.LightBlue;
	                item.HoverElement.Fill.BackColor = Color.DeepSkyBlue;
	                item.ValueElement.Fill.BackColor = Color.DodgerBlue;
	                item.SelectedValueElement.Fill.BackColor = Color.Blue;
	
	                item.Fill.GradientStyle = Telerik.WinControls.GradientStyles.Solid;
	                item.HoverElement.Fill.GradientStyle = Telerik.WinControls.GradientStyles.Solid;
	                item.ValueElement.Fill.GradientStyle = Telerik.WinControls.GradientStyles.Solid;
	                item.SelectedValueElement.Fill.GradientStyle = GradientStyles.Solid;
	            }
	
	{{endregion}}



#### __[VB.NET]__

{{region Background}}
	
	        For Each item As RatingStarVisualElement In Me.RadRating1.Items
	            item.Fill.BackColor = Color.LightBlue
	            item.HoverElement.Fill.BackColor = Color.DeepSkyBlue
	            item.ValueElement.Fill.BackColor = Color.DodgerBlue
	            item.SelectedValueElement.Fill.BackColor = Color.Blue
	
	            item.Fill.GradientStyle = Telerik.WinControls.GradientStyles.Solid
	            item.HoverElement.Fill.GradientStyle = Telerik.WinControls.GradientStyles.Solid
	            item.ValueElement.Fill.GradientStyle = Telerik.WinControls.GradientStyles.Solid
	            item.SelectedValueElement.Fill.GradientStyle = GradientStyles.Solid
	        Next
	
	        '#End Region
	
	        '#Region "CustomShape"
	
	        For i As Integer = 0 To 4
	            Dim myShape As New CustomShapeElement()
	            myShape.Fill.BackColor = Color.LightBlue
	            myShape.HoverElement.Fill.BackColor = Color.DeepSkyBlue
	            myShape.ValueElement.Fill.BackColor = Color.DodgerBlue
	            myShape.SelectedValueElement.Fill.BackColor = Color.Blue
	
	            myShape.Fill.GradientStyle = Telerik.WinControls.GradientStyles.Solid
	            myShape.HoverElement.Fill.GradientStyle = Telerik.WinControls.GradientStyles.Solid
	            myShape.ValueElement.Fill.GradientStyle = Telerik.WinControls.GradientStyles.Solid
	            myShape.SelectedValueElement.Fill.GradientStyle = GradientStyles.Solid
	            Me.RadRating1.Items.Add(myShape)
	        Next
	
	        ' #End Region
	    End Sub
	
	#Region "CustomShapeClasses"
	
	    Public Class CustomShapeElement
	        Inherits RatingVisualElement
	        Protected Overrides Function GetShape() As ElementShape
	            Return New CustomShape()
	        End Function
	
	        Protected Overrides ReadOnly Property ThemeEffectiveType() As Type
	            Get
	                Return GetType(RatingVisualElement)
	            End Get
	        End Property
	    End Class
	
	    Public Class CustomShape
	        Inherits ElementShape
	        Public Overrides Function CreatePath(bounds As Rectangle) As GraphicsPath
	            Dim path As New GraphicsPath()
	            path.AddEllipse(bounds)
	
	            Return path
	        End Function
	    End Class
	
	#End Region
	End Class

![rating-customization 001](images/rating-customization001.png)![rating-customization 002](images/rating-customization002.png)

## Custom Shape

By default __RadRating__ supports three main element shapes: Stars, Diamonds and Hearts.
          If a different kind of shape is needed, __RadRating__ allows you to create and use your own custom visual
          elements. The following example demonstrates creating a circle visual element:
        

#### __[C#]__

{{region CustomShape}}
	            
	            for (int i = 0; i < 5; i++)
	            {
	                CustomShapeElement myShape = new CustomShapeElement();
	                myShape.Fill.BackColor = Color.LightBlue;
	                myShape.HoverElement.Fill.BackColor = Color.DeepSkyBlue;
	                myShape.ValueElement.Fill.BackColor = Color.DodgerBlue;
	                myShape.SelectedValueElement.Fill.BackColor = Color.Blue;  
	                
	                myShape.Fill.GradientStyle = Telerik.WinControls.GradientStyles.Solid;
	                myShape.HoverElement.Fill.GradientStyle = Telerik.WinControls.GradientStyles.Solid;
	                myShape.ValueElement.Fill.GradientStyle = Telerik.WinControls.GradientStyles.Solid;
	                myShape.SelectedValueElement.Fill.GradientStyle = GradientStyles.Solid;
	                this.radRating1.Items.Add(myShape);
	            }
	    
	{{endregion}}



#### __[VB.NET]__

{{region CustomShape}}
	
	        For i As Integer = 0 To 4
	            Dim myShape As New CustomShapeElement()
	            myShape.Fill.BackColor = Color.LightBlue
	            myShape.HoverElement.Fill.BackColor = Color.DeepSkyBlue
	            myShape.ValueElement.Fill.BackColor = Color.DodgerBlue
	            myShape.SelectedValueElement.Fill.BackColor = Color.Blue
	
	            myShape.Fill.GradientStyle = Telerik.WinControls.GradientStyles.Solid
	            myShape.HoverElement.Fill.GradientStyle = Telerik.WinControls.GradientStyles.Solid
	            myShape.ValueElement.Fill.GradientStyle = Telerik.WinControls.GradientStyles.Solid
	            myShape.SelectedValueElement.Fill.GradientStyle = GradientStyles.Solid
	            Me.RadRating1.Items.Add(myShape)
	        Next
	
	        ' #End Region
	    End Sub
	
	#Region "CustomShapeClasses"
	
	    Public Class CustomShapeElement
	        Inherits RatingVisualElement
	        Protected Overrides Function GetShape() As ElementShape
	            Return New CustomShape()
	        End Function
	
	        Protected Overrides ReadOnly Property ThemeEffectiveType() As Type
	            Get
	                Return GetType(RatingVisualElement)
	            End Get
	        End Property
	    End Class
	
	    Public Class CustomShape
	        Inherits ElementShape
	        Public Overrides Function CreatePath(bounds As Rectangle) As GraphicsPath
	            Dim path As New GraphicsPath()
	            path.AddEllipse(bounds)
	
	            Return path
	        End Function
	    End Class
	
	#End Region
	End Class



#### __[C#]__

{{region CustomShapeClasses}}
	        
	    public class CustomShapeElement : RatingVisualElement
	    {
	        protected override ElementShape GetShape()
	        {
	            return new CustomShape();
	        }
	            
	        protected override Type ThemeEffectiveType
	        {
	            get
	            {
	                return typeof(RatingVisualElement);
	            }
	        }
	    }
	        
	    public class CustomShape : ElementShape
	    {
	        public override GraphicsPath CreatePath(Rectangle bounds)
	        {
	            GraphicsPath path = new GraphicsPath();
	            path.AddEllipse(bounds);
	    
	            return path;
	        }
	    }
	
	{{endregion}}



#### __[VB.NET]__

{{region CustomShapeClasses}}
	
	    Public Class CustomShapeElement
	        Inherits RatingVisualElement
	        Protected Overrides Function GetShape() As ElementShape
	            Return New CustomShape()
	        End Function
	
	        Protected Overrides ReadOnly Property ThemeEffectiveType() As Type
	            Get
	                Return GetType(RatingVisualElement)
	            End Get
	        End Property
	    End Class
	
	    Public Class CustomShape
	        Inherits ElementShape
	        Public Overrides Function CreatePath(bounds As Rectangle) As GraphicsPath
	            Dim path As New GraphicsPath()
	            path.AddEllipse(bounds)
	
	            Return path
	        End Function
	    End Class
	
	#End Region
	End Class

![rating-customization 003](images/rating-customization003.png)
