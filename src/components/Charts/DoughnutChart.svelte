<script>
  import { onMount } from "svelte";
  import Chart from "Chart.js";

  let description =
    "Donut Chart (also known as Doughnut chart) is a variation on a Pie chart except it has a round hole in the center which makes it look like a donut, hence the name. This empty space can be used to display additional data.";

  function createDoughnut() {
    var ctx = document.getElementById("doughnut-chart");
    let myChart = new Chart(ctx, {
      type: "doughnut",
      data: {
        labels: ["Africa", "Asia", "Europe", "Latin America", "North America"],
        datasets: [
          {
            label: "Population (millions)",
            backgroundColor: [
              "#3e95cd",
              "#8e5ea2",
              "#3cba9f",
              "#e8c3b9",
              "#c45850"
            ],
            data: [2478, 5267, 734, 784, 433]
          }
        ]
      },
      options: {
        title: {
          display: true,
          text: "Predicted world population (millions) in 2050"
        }
      }
    });
  }
  onMount(createDoughnut);
</script>

<style>
  .heading {
    margin: 1rem 0;
    font-weight: 300;
    font-size: 1rem;
  }
  .sub-heading {
    margin-bottom: 2.5rem;
    color: rgb(156, 156, 156);
    font-size: 0.75rem;
  }
  .chart {
    margin: 1rem 1rem 0 0;
    padding: 30px 20px;
    background-color: rgb(255, 255, 255);
    width: 50%;
    flex-direction: column;
  }
  @media (max-width: 480px) {
    .chart {
      padding: 10px;
      margin: 1rem;
      background-color: rgb(255, 255, 255);
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
      flex: 1;
    }
  }
</style>

<div class="chart">
  <h4 class="heading">Doughnut Chart</h4>
  <p class="sub-heading">{description}</p>
  <canvas id="doughnut-chart" width="4%" height="3%" />
</div>
