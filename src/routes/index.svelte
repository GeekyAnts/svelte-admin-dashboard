<script>
  import BarChart from "../components/Charts/BarChart.svelte";
  import LineChart from "../components/Charts/LineChart.svelte";
  import PieChart from "../components/Charts/PieChart.svelte";
  import DoughnutChart from "../components/Charts/DoughnutChart.svelte";
</script>

<style>
  p {
    margin: 1em auto;
  }

  .main {
    flex: 1;
    margin-left: 30px;
    color: rgb(142, 141, 141);
  }
  .main-title {
    margin-bottom: 10px;
    font-weight: 300;
    color: rgb(94, 94, 94);
  }
  .charts {
    width: 100%;
    display: flex;
    flex-direction: column;
    flex: 1;
  }

  .inner-charts {
    flex: 1;
    flex-direction: row;
  }

  @media (max-width: 480px) {
    .main {
      flex: 1;
      margin-top: 3rem;
    }
  }

  @media screen and (max-width: 640px) {
    .inner-charts {
      flex: 1;
      flex-direction: column;
    }
  }

  @media screen and (min-width: 768px) {
    .inner-charts {
      flex: 1;
      flex-direction: row;
      display: inline-flex;
    }
  }
</style>

<svelte:head>
  <title>Dashboard</title>
</svelte:head>

<div class="main">
  <h4 class="main-title">DASHBOARD</h4>
  <p>Welcome to the unique Material Design admin web app experience!</p>
</div>

<div class="charts">
  <div class="inner-charts">
    <LineChart />
    <PieChart />
  </div>

  <div class="inner-charts">
    <DoughnutChart />
    <BarChart />
  </div>
</div>
