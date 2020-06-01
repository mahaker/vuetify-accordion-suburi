<template>
  <v-row justify="center">
    <v-expansion-panels flat accordion multiple>
      <v-expansion-panel disabled>
        <v-expansion-panel-header>
          <v-simple-table
            dark
            :height="headerHeight"
          >
            <template #default>
              <tbody>
                <tr>
                  <td class="group-width"></td>
                  <td class="unperformed-num-width">y/20</td>
                  <td class="performed-num-width" v-for="(n, idx) in 5" :key="idx">レベル{{ n }}</td>
                </tr>
              </tbody>
            </template>
          </v-simple-table>
        </v-expansion-panel-header>
      </v-expansion-panel>
      <v-expansion-panel
        v-for="(group,i) in groups"
        :key="i"
      >
        <v-expansion-panel-header>
          <v-simple-table
            :height="headerHeight"
          >
            <template #default>
              <tbody>
                <tr>
                  <td class="group-width">{{ group }}</td>
                  <td class="unperformed-num-width">x/5</td>
                  <td class="performed-num-width" v-for="(n, idx) in 5" :key="idx">{{ n }}</td>
                </tr>
              </tbody>
            </template>
          </v-simple-table>
        </v-expansion-panel-header>
        <v-expansion-panel-content>
          <v-simple-table>
            <template #default>
              <tbody>
                <tr v-for="(item,idx2) in items" :key="idx2">
                  <td class="group-width"></td>
                  <td class="item-width">{{ item }}</td>
                  <td class="performed-check-width" v-for="(n, idx) in 5" :key="idx">
                    <input type="check" />
                  </td>
                </tr>
              </tbody>
            </template>
          </v-simple-table>
        </v-expansion-panel-content>
      </v-expansion-panel>
    </v-expansion-panels>
  </v-row>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'HelloWorld',
  data: () => ({
      headerHeight: 50,
      select1: true,
      groups: [
        "分類1",
        "分類2",
        "分類3",
        "分類4",
      ],
      items: [
        "項目1",
        "項目2",
        "項目3",
      ]
    }),
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
th, td {
  border: 1px solid;
  border-collapse: collapse;
}

.group-width {
  /* width: 300px; */
  min-width: 100px;
  max-width: 100px;
}

.unperformed-num-width, .item-width {
  /* width: 100px; */
  min-width: 50px;
  max-width: 50px;
}

.performed-num-width, .performed-check-width {
  /* width: 50px; */
  min-width: 50px;
  max-width: 50px;
}
</style>
