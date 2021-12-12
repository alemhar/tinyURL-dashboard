<template>
  <div>
    <Dashboard />
    <div class="row">
      <div id="links" class="col-4">
        <div class="row">
          <div id="links-label" class="py-2">Your recent TinyURLs</div>
        </div>
        <tinyurl
          v-for="tinyurl in tinyurls"
          :key="tinyurl.id"
          :short_url="tinyurl.shortUrl"
          :url="tinyurl.url"
          :elapse_time="tinyurl.elapseTime"
          :clicks="tinyurl.clicks"
        >
        </tinyurl>

        <div class="row fixed-bottom">
          <div class="col-4">
            <div id="links-label" class="py-2 row">
              <div class="col fw-light">5 Links</div>
              <div class="col fw-light" style="text-align: right">
                392 Clicks
              </div>
            </div>
          </div>
        </div>
      </div>

      <div id="charts" class="col-8">
        <div class="row">
          <div class="py-2 text-secondary">Analytics for all links</div>
          <div class="h3">Dashboard</div>

          <div class="row">
            <total-count
              v-for="totalCount in totalCounts"
              :key="totalCount.id"
              :name="totalCount.name"
              :count="totalCount.count"
            >
            </total-count>
          </div>
          <div class="m-3 p-2" style="background: white">
            <div class="h3">Traffic Overtime</div>

            <bar-chart :width="1200" :height="400"></bar-chart>
          </div>
          <div class="m-3 p-2" style="background: white">
            <div class="h3">Traffic Region</div>

            <MapChart
              :countryData="regionClicks"
              highColor="#1e21a8"
              lowColor="#8a8cff"
              countryStrokeColor="#909090"
              defaultCountryFillColor="#dadada"
              :currencyAdd=false
              LangUser="en"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Dashboard from "./components/Dashboard.vue";
import Tinyurl from "./components/TinyUrl.vue";
import TotalCount from "./components/TotalCounts.vue";
import BarChart from "./components/BarChart.vue";
import MapChart from "vue-chart-map";
//import { shuffle } from "lodash";

export default {
  name: "App",
  components: {
    Dashboard,
    Tinyurl,
    TotalCount,
    BarChart,
    MapChart
  },
  data() {
    return {
      regionClicks: { US: 100, CA: 7, GB: 8, IE: 14, ES: 21, PH: 50 },
      tinyurls: [
        {
          id: 1,
          shortUrl: "turl.com/32rs34cc",
          url: "https://google.com/python-django-vue",
          elapseTime: "5",
          clicks: "82",
        },
        {
          id: 2,
          shortUrl: "turl.com/51rx34fc",
          url: "https://google.com/php-laravel-vue",
          elapseTime: "9",
          clicks: "322",
        },
        {
          id: 3,
          shortUrl: "turl.com/80er35xc",
          url: "https://google.com/javascript-express-vue",
          elapseTime: "15",
          clicks: "123",
        },
        {
          id: 4,
          shortUrl: "turl.com/21jk12hg",
          url: "https://google.com/ruby-rails-vue",
          elapseTime: "25",
          clicks: "243",
        },
      ],
      totalCounts: [
        {
          id: 1,
          name: "Active Links",
          count: 5,
        },
        {
          id: 2,
          name: "Total Human Clicks",
          count: 352,
        },
        {
          id: 3,
          name: "Unique Clicks",
          count: 211,
        },
        {
          id: 4,
          name: "Unique Vistors",
          count: 210,
        },
      ],
    };
  },
  methods: {},
};
</script>

<style scoped>
#links {
  background: lightgray;
}
#charts {
  background: #f4f4f4;
}
#links-label {
  background: #082c5f;
  color: white;
  font-weight: bold;
  padding-left: 20px;
}
</style>
