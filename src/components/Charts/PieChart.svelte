<script>
  import Chart from "chart.js";
  import { onMount } from "svelte";

  let description =
    "A pie chart (or a circle chart) is a circular statistical graphic, which is divided into slices to illustrate numerical proportion. In a pie chart, the arc length of each slice (and consequently its central angle and area), is proportional to the quantity it represents.";

  const chartData = {
    labels: ["Red", "Blue", "Yellow", "Green", "Purple", "Orange"],
    datasets: [
      {
        label: "# of Votes",
        data: [12, 19, 3, 5, 2, 3],
        backgroundColor: [
          "rgba(255, 99, 132, 0.2)",
          "rgba(54, 162, 235, 0.2)",
          "rgba(255, 206, 86, 0.2)",
          "rgba(75, 192, 192, 0.2)",
          "rgba(153, 102, 255, 0.2)",
          "rgba(255, 159, 64, 0.2)"
        ],
        borderColor: [
          "rgba(255, 99, 132, 1)",
          "rgba(54, 162, 235, 1)",
          "rgba(255, 206, 86, 1)",
          "rgba(75, 192, 192, 1)",
          "rgba(153, 102, 255, 1)",
          "rgba(255, 159, 64, 1)"
        ],
        borderWidth: 1
      }
    ]
  };
  const chartOptions = {
    scales: {
      yAxes: [
        {
          ticks: {
            beginAtZero: true
          }
        }
      ]
    },
    layout: {
      padding: {
        left: 20,
        right: 20,
        top: 20,
        bottom: 0
      }
    }
  };

  function createChart() {
    var ctx = document.getElementById("myPieChart");
    var myChart = new Chart(ctx, {
      type: "pie",
      data: chartData,
      options: chartOptions
    });
  }

  onMount(createChart);
</script>

<style>
  .chart {
    margin: 1rem 0 0 1rem;
    padding: 2rem 1rem;
    background-color: rgb(255, 255, 255);
    width: 50%;
  }

  .heading {
    margin: 1rem 0;
    font-weight: 300;
    font-size: 1rem;
  }
  .sub-heading {
    margin-bottom: 1.5rem;
    color: rgb(156, 156, 156);
    font-size: 0.75rem;
  }

  @media (max-width: 480px) {
    .chart {
      padding: 10px;
      margin: 1rem;
      width: 90%;
      flex: 1;
    }
  }

  @media screen and (max-width: 768px) {
    .chart {
      padding: 10px;
      margin: 1rem;
      width: 90%;
      flex: 1;
    }
  }
  @media screen and (min-width: 769px) {
    .chart {
      margin-left: 10px;
      padding: 10px;
      /* width: 10%; */
      flex: 1;
    }
  }
</style>

<div class="chart">
  <h4 class="heading">Pie Chart</h4>
  <p class="sub-heading">{description}</p>
  <canvas id="myPieChart" width="4%" height="3%" />
</div>
