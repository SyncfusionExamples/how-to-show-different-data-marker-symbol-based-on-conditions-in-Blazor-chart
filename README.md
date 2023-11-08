# How-to-show-different-data-marker-symbol-based-on-conditions-in-Blazor-chart

This KB article explain how to show different data marker symbols based on the conditions in the [Blazor Chart](https://www.syncfusion.com/blazor-components/blazor-charts).

We can show different data marker symbols based on the conditions by using [OnPointRender](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartEvents.html#Syncfusion_Blazor_Charts_ChartEvents_OnPointRender) event. This event triggers before each point for the series is rendered.

The following properties are available in the [PointRenderEventArgs](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.PointRenderEventArgs.html).

•	[Border](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.PointRenderEventArgs.html#Syncfusion_Blazor_Charts_PointRenderEventArgs_Border) – Specifies the color and the width of the point border.

•	[Fill](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.PointRenderEventArgs.html#Syncfusion_Blazor_Charts_PointRenderEventArgs_Fill) – Specifies the fill color of the point.

•	[Height](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.PointRenderEventArgs.html#Syncfusion_Blazor_Charts_PointRenderEventArgs_Height) – Specifies the current point’s height.

•	[Shape](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.PointRenderEventArgs.html#Syncfusion_Blazor_Charts_PointRenderEventArgs_Shape) – Specifies the marker shape of the point.

•	[Width](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.PointRenderEventArgs.html#Syncfusion_Blazor_Charts_PointRenderEventArgs_Width) – Specifies the current point’s width.

We can customize the marker shape  based on Y value by specifying the [Shape](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.PointRenderEventArgs.html#Syncfusion_Blazor_Charts_PointRenderEventArgs_Shape) property of the [PointRenderEventArgs](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.PointRenderEventArgs.html).

The below code example illustrates this.

**C#**

```cshtml
@using Syncfusion.Blazor.Charts

<SfChart>   
    <ChartEvents OnPointRender="@PointRender"></ChartEvents>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@ConsumerReports" XName="X" YName="Y" Type="ChartSeriesType.Line">
            <ChartMarker Visible="true" Height="10" Width="10" />
        </ChartSeries>
    </ChartSeriesCollection>
</SfChart>

@code {
    
    public class ChartData
    {
        public double X { get; set; }
        public double Y { get; set; }
    }

    public List<ChartData> ConsumerReports = new List<ChartData>
    {
        new ChartData{ X= 2005, Y= 25 },
        new ChartData{ X= 2006, Y= 15 },
        new ChartData{ X= 2007, Y= 45 },
        new ChartData{ X= 2008, Y= 30},
        new ChartData{ X= 2009, Y= 20 },
        new ChartData{ X= 2010, Y= 35 },
        new ChartData{ X= 2011, Y= 50 },
        new ChartData{ X= 2012, Y= 45 },
        new ChartData{ X= 2013, Y= 25 },
        new ChartData{ X= 2014, Y= 35 },
        new ChartData{ X= 2015, Y= 20 }
    };
    public void PointRender(PointRenderEventArgs args)
    {
        if(args.Point.YValue <= 20)
        {
            args.Shape = ChartShape.InvertedTriangle;
            args.Fill = "red";
            args.Border.Color = "red";
        }
        if(args.Point.YValue >20 && args.Point.YValue < 40)
        {
            args.Shape = ChartShape.Diamond;
            args.Fill = "blue";
            args.Border.Color = "blue";
        }
        if (args.Point.YValue >= 40)
        {
            args.Shape = ChartShape.Triangle;
            args.Fill = "green";
            args.Border.Color = "green";
        }
    }
}

```
The following screenshot illustrate the output of the above code snippet.

**Output:**

![](/different-marker-symbol-based-on-condition.png)

**Conclusion**

I hope you enjoyed learning how to show different data marker symbols based on conditions in Blazor Chart Component.

You can refer to our [Blazor Chart feature tour](https://www.syncfusion.com/blazor-components/blazor-charts) page to know about its other groundbreaking feature representations and [documentation](https://blazor.syncfusion.com/documentation/chart/getting-started), and how to quickly get started for configuration specifications. You can also explore our [Blazor Chart example](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap5) to understand how to create and manipulate data.

For current customers, you can check out our components from the [License and Downloads](https://www.syncfusion.com/sales/teamlicense) page. If you are new to Syncfusion, you can try our 30-day [free trial](https://www.syncfusion.com/downloads/blazor) to check out our other controls.

If you have any queries or require clarifications, please let us know in the comments section below. You can also contact us through our [support forums](https://www.syncfusion.com/forums), [Direct-Trac](https://support.syncfusion.com/create), or [feedback portal](https://www.syncfusion.com/feedback/blazor-components?control=charts). We are always happy to assist you!


