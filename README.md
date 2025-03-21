# Charts - SVG Chart Rendering

**Charts** is a zero-dependency PHP library for generating SVG charts. It enables easy creation of SVG-based charts directly from PHP, with no additional dependencies required.

## Features

- Simple, intuitive API for chart creation
- Lightweight, with no external dependencies
- Supports various chart types: line charts, bar charts, stacked charts, and mixed charts
- Fully customizable and extendable
- Outputs pure SVG, allowing for:
  - Embedding in PDFs, [view example PDF report](https://raw.githubusercontent.com/maantje/charts/refs/heads/main/examples/output/report.pdf)

## Installation

To get started, install the package via composer:

```bash
composer require maantje/charts
```

## Usage Examples

Below are some examples of the types of charts you can create using this library. Click on the links to view the source code for each example.

- [Example Usage With mPDF](#example-usage-with-mpdf)
- [Simple Line Chart](#simple-line-chart)
- [Curved Line Chart](#curved-line-chart)
- [Step Line Chart](#step-line-chart)
- [Area Line Chart](#area-line-chart)
- [Bar Chart](#bar-chart)
- [Stacked Bar Chart](#stacked-bar-chart)
- [Grouped Bar Chart](#grouped-bar-chart)
- [Advanced Line Chart](#advanced-line-chart)
- [Advanced Bar Chart](#advanced-bar-chart)
- [Mixed Chart](#mixed-chart)
- [Pie Chart](#pie-chart)

### Example Usage With mPDF
[📄 View PDF document](https://raw.githubusercontent.com/maantje/charts/refs/heads/main/examples/output/report.pdf)  
[View source](./examples/pdf/mpdf.php)

### Simple Line Chart
![Simple Line Chart](./examples/output/line-chart.svg)  
[View source](./examples/line-chart.php)

### Curved Line Chart
![Curved Line Chart](./examples/output/curved-line-chart.svg)  
[View source](./examples/curved-line-chart.php)

### Step line chart
![Step line chart](./examples/output/step-line-chart.svg)  
[View source](./examples/step-line-chart.php)

### Area line chart
![Area line chart](./examples/output/area-line-chart.svg)  
[View source](./examples/area-line-chart.php)

### Bar Chart
![Bar Chart](./examples/output/bar-chart.svg)  
[View source](./examples/bar-chart.php)

### Stacked Bar Chart
![Stacked Bar Chart](./examples/output/stacked-bar-chart.svg)  
[View source](./examples/stacked-bar-chart.php)

### Grouped Bar Chart
![Grouped Bar Chart](./examples/output/grouped-bar-chart.svg)  
[View source](./examples/grouped-bar-chart.php)

### Advanced Line Chart
![Advanced Line Chart](./examples/output/advanced-line-chart.svg)  
[View source](./examples/advanced-line-chart.php)

### Advanced Bar Chart
![Advanced Bar Chart](./examples/output/advanced-bar-chart.svg)  
[View source](./examples/advanced-bar-chart.php)

### Mixed chart
![Mixed chart](./examples/output/mixed-chart.svg)  
[View source](./examples/mixed-chart.php)

### Pie chart
![Pie chart](./examples/output/pie-chart.svg)  
[View source](./examples/pie-chart.php)

## Usage

### Creating a Chart

You can create different types of charts using the provided classes. Below are examples of how to create a simple bar chart and a line chart.

#### Simple Bar Chart

```php
use Maantje\Charts\Bar\Bar;
use Maantje\Charts\Bar\Bars;
use Maantje\Charts\Chart;

$chart = new Chart(
    series: [
        new Bars(
            bars: [
                new Bar(name: 'Jan', value: 222301),
                new Bar(name: 'Feb', value: 189242),
                new Bar(name: 'Mar', value: 144922),
            ],
        ),
    ],
);

echo $chart->render();
```

#### Simple Line Chart

```php
use Maantje\Charts\Chart;
use Maantje\Charts\Line\Line;
use Maantje\Charts\Line\Lines;
use Maantje\Charts\Line\Point;

$chart = new Chart(
    series: [
        new Lines(
            lines: [
                new Line(
                    points: [
                        new Point(x: 0, y: 0),
                        new Point(x: 100, y: 4),
                        new Point(x: 200, y: 12),
                        new Point(x: 300, y: 8),
                    ],
                ),
                new Line(
                    points: [
                        [0, 0],
                        [100, 4],
                        [200, 12],
                        [300, 8],
                    ],
                ),
            ],
        ),
    ],
);

echo $chart->render();
```

#### Annotations

You can add annotations to your charts for better visualization.

```php
use Maantje\Charts\Annotations\PointAnnotation;
use Maantje\Charts\YAxis;

$chart = new Chart(
    yAxis: new YAxis(
        annotations: [
            new PointAnnotation(x: 200, y: 120, label: 'Important Point'),
        ],
    ),
    // ...
);
```

## License

The MIT License (MIT). Please see [License File](LICENSE) for more information.
