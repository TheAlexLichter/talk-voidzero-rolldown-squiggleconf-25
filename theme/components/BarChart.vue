<script setup lang="ts">
import { Bar } from "vue-chartjs";
import {
  Chart,
  CategoryScale,
  LinearScale,
  BarElement,
  Title,
  Tooltip,
  Legend,
} from "chart.js";

Chart.register(CategoryScale, LinearScale, BarElement, Title, Tooltip, Legend);

interface ToolData {
  name: string;
  value: number; // Lower is faster
}

const { unit = 'ms', ...props } = defineProps<{
  title: string;
  tools: ToolData[];
  unit?: string;
  unitLegend?: string;
}>();

const formatValue = (val: number) => {
  // Always use dot as decimal separator
  return val.toLocaleString('en-US', { maximumFractionDigits: 6 });
};

const chartData = {
  labels: props.tools.map((t) => t.name),
  datasets: [
    {
      data: props.tools.map((t) => Number(formatValue(t.value))),
      backgroundColor: props.tools.map((_, i) => {
        const colors = [
          "#4f8cff",
          "#ffb347",
          "#34c759",
          "#ff3b30",
          "#a259ff",
          "#ffd60a",
        ];
        return colors[i % colors.length];
      }),
      borderRadius: 3,
      minBarLength: 10,
    },
  ],
};

const chartOptions = {
  responsive: true,
  plugins: {
    legend: {
      display: false,
    },
    title: {
      display: true,
      text: props.title,
      color: "white",
    },
    tooltip: {
      callbacks: {
        label: (ctx: any) => {
          const val = ctx.parsed.x ?? ctx.parsed.y;
          return `${formatValue(val)}${unit ? ' ' + unit : ''}`;
        }
      }
    }
  },
  indexAxis: "y" as const,
  scales: {
    x: {
      title: {
        display: true,
        text: props.unitLegend || "",
        color: "white",
      },
      ticks: {
        color: "white",
        callback: (val: any) => formatValue(val),
      },
      grid: {
        display: true,
        color: "#e0e0e0",
      },
    },
    y: {
      grid: {
        display: true,
        color: "#e0e0e0",
      },
      ticks: {
        color: "white",
      },
      title: {
        display: false,
        color: "white",
      },
    },
  },
};
</script>

<template>
  <div class="h-80 mx-auto">
    <Bar class="mx-auto" style="width: 800px !important; height: 400px !important" :data="chartData" :options="chartOptions" />
  </div>
</template>
