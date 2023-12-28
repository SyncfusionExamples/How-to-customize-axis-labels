# How-to-customize-axis-labels

This article explains how to customize axis labels in Blazor Chart Component.

**Customizing axis labels in Blazor chart**

[Blazor Chart](https://www.syncfusion.com/blazor-components/blazor-charts) provides various customization options for axis labels using [OnAxisLabelRender](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartEvents.html#Syncfusion_Blazor_Charts_ChartEvents_OnAxisLabelRender) event. This event triggers before each axis label renders. 

Below properties in event args can be used to customize the label rendering.

- [LabelStyle](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisLabelRenderEventArgs.html#Syncfusion_Blazor_Charts_AxisLabelRenderEventArgs_LabelStyle) – Specifies the font information of the axis label with following properties. 

|**Properties**|**Description**|
| :- | :- |
|**Color**|To customize the color of the text.|
|**FontFamily**|To customize the font family of label.|
|**FontStyle**|To customize the font style.|
|**FontWeight**|To customize the font weight.|
|**Opacity**|To customize the transparency of the text.| 

The properties such as `Color`, `FontFamily`, `FontStyle`, `FontWeight` and `Opacity` of the axis label can be customized by using [LabelStyle](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisLabelRenderEventArgs.html#Syncfusion_Blazor_Charts_AxisLabelRenderEventArgs_LabelStyle) event argument of the [OnAxisLabelRender](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartEvents.html#Syncfusion_Blazor_Charts_ChartEvents_OnAxisLabelRender) event. 

The following code example illustrates how to customize the color of the axis labels in Blazor chart.

**Index.razor**

```cshtml

@using Syncfusion.Blazor.Charts

<SfChart>
    <ChartEvents OnAxisLabelRender="AxisLabelEvent"></ChartEvents>

    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category" LabelPosition="AxisPosition.Inside"></ChartPrimaryXAxis>

    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
</SfChart>

@code {

    public class SalesInfo
    {
        public string Month { get; set; }
        public double SalesValue { get; set; }
    }

    public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };

    public void AxisLabelEvent(AxisLabelRenderEventArgs args)
    {
        if (args.Axis.Name == "PrimaryXAxis")
        {
            args.LabelStyle.Color = "Red";
        }         
    }

}

```

The following screenshot illustrates the output of the above code snippet.

**Output:**

![Axis label customization](/label-customization.png)

**Conclusion**

I hope you enjoyed learning how to customize axis label in Blazor Chart Component.

You can refer to our [Blazor Chart feature tour](https://www.syncfusion.com/blazor-components/blazor-charts) page to know about its other groundbreaking feature representations and [documentation](https://blazor.syncfusion.com/documentation/chart/getting-started), and how to quickly get started for configuration specifications. You can also explore our [Blazor Chart example](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap5) to understand how to create and manipulate data.

For current customers, you can check out our components from the [License and Downloads](https://www.syncfusion.com/sales/teamlicense) page. If you are new to Syncfusion, you can try our 30-day [free trial](https://www.syncfusion.com/downloads/blazor) to check out our other controls.

If you have any queries or require clarifications, please let us know in the comments section below. You can also contact us through our [support forums](https://www.syncfusion.com/forums), [support portal](https://support.syncfusion.com/create), or [feedback portal](https://www.syncfusion.com/feedback/blazor-components?control=charts). We are always happy to assist you!