# Chart.JS

Chart.JS is a great little tool online that you can use inside your HTML documents to visualize charts within your website. The online database library contains tons of customization and many different styles of charts. Using the `<canvas>` tag you start the marking of your HTML to integrate a chart.

```html
<script src="https://cdn.jsdelivr.net/npm/chart.js@2.8.0"></script>
```

The script tag containing the source marks up the HTML to point towards the Chart.js CDN. This allows any machine to utilize the online database without having to download it to the local machine before using it. This decreases the time required to load a page.

```html
<canvas id="myChart"></canvas>
```

The `<canvas>` tag including an ID to point the Javascript where to go when creating a new chart.

```js
var ctx = document.getElementById('myChart').getContext('2d');
var chart = new Chart(ctx, {
    // The type of chart we want to create
    type: 'line',

    // The data for our dataset
    data: {
        labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
        datasets: [{
            label: 'My First dataset',
            backgroundColor: 'rgb(255, 99, 132)',
            borderColor: 'rgb(255, 99, 132)',
            data: [0, 10, 5, 2, 20, 30, 45]
        }]
    },

    // Configuration options go here
    options: {}
});
```

Above is the minimum required Javascript needed to form the chart within your HTML. Point your HTML ID to match the Javascript, input your data and labels and you're good to go.
