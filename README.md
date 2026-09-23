# Conditional Data Marker Symbols in Syncfusion Blazor Chart

## Overview

This sample demonstrates how to customize marker symbols dynamically in Syncfusion [Blazor Charts](https://www.syncfusion.com/blazor-components/blazor-charts) based on individual data point values. The implementation uses the `OnPointRender` event to evaluate each chart point before rendering and applies different marker shapes, fill colors, and border colors according to predefined value thresholds.

By customizing marker symbols based on business conditions, the chart provides immediate visual differentiation between data categories. This technique improves readability and helps users quickly identify trends, exceptions, and threshold-based patterns directly within the chart visualization.

## Key Features

- Uses the `SfChart` component to render a line chart.
- Binds data through the `ChartSeries.DataSource` property.
- Maps data fields using:
  - `XName`
  - `YName`
- Enables marker rendering through:
  - `ChartMarker.Visible`
  - `ChartMarker.Height`
  - `ChartMarker.Width`
- Handles the `ChartEvents.OnPointRender` event for per-point customization.
- Uses `PointRenderEventArgs` to modify:
  - `Shape`
  - `Fill`
  - `Border.Color`
- Customizes marker appearance according to `args.Point.YValue`.
- Applies the following marker symbols:
  - `ChartShape.InvertedTriangle`
  - `ChartShape.Diamond`
  - `ChartShape.Triangle`
- Assigns matching fill and border colors for each marker category.

## Prerequisites

- [Visual Studio 2022](https://visualstudio.microsoft.com/vs/) or [Visual Studio Code](https://code.visualstudio.com/)
- [.NET SDK](https://dotnet.microsoft.com/en-us/download/dotnet) compatible with the project's target framework

## How to Run the Project

**Visual Studio 2022**

1. Clone or download this repository.
2. Open the project file:

   `BlazorApp1/BlazorApp1.csproj`

3. Restore NuGet packages.
4. Build the project.
5. Press `Ctrl + F5` to run the application.

**Visual Studio Code**

1. Open the repository folder in Visual Studio Code.
2. Open the integrated terminal.
3. Navigate to the project directory.

```bash
cd BlazorApp1
dotnet restore
dotnet run
```

4. Open the local URL displayed in the terminal after application startup.

## Project Structure

`Pages/Index.razor` - Hosts the Syncfusion chart sample demonstrating conditional marker symbol customization.

## Support and Feedback

- For general product questions, visit the [Syncfusion Community Forum](https://www.syncfusion.com/forums) or [Syncfusion Support](https://www.syncfusion.com/support).
- To report an issue specific to this sample, open a GitHub issue in this repository.
- Refer to the Syncfusion Chart documentation for event-based customization using `OnPointRender`: https://help.syncfusion.com/chart-sdk/blazor/charts/getting-started

## License

This is a Syncfusion sample project provided to demonstrate product usage. Review the [Syncfusion license terms](https://www.syncfusion.com/sales/pricing?category=ui-components) before using Syncfusion components in your own applications.