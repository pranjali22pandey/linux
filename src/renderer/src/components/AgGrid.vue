<template>
  <div class="ag-grid-container">
    <ag-grid-vue
      id="myGrid"
      :row-data="rowData"
      :column-defs="colDefs"
      :default-col-def="defaultColDef"
      class="ag-theme-alpine"
      :suppress-row-click-selection="true"
      style="width: 100%; height: 100%"
      :pagination="true"
      :pagination-page-size="paginationPageSize"
      :pagination-page-size-selector="paginationPageSizeSelector"
      @grid-ready="onGridReady"
    >
    </ag-grid-vue>
  </div>
</template>

<script>
import { ref, onBeforeMount, shallowRef } from "vue";
import "ag-grid-community/styles/ag-grid.css";
import "ag-grid-community/styles/ag-theme-alpine.css";
import { AgGridVue } from "ag-grid-vue3";
import RowData from "../constants/rowData.js";
import colData from "../constants/colData.js";
export default {
  name: "AgGrid",
  components: {
    AgGridVue,
  },
  setup() {
    const gridApi = shallowRef();
    const rowData = ref(null);
    const rowSelection = ref(null);
    const paginationPageSize = ref(null);
    const paginationPageSizeSelector = ref(null);

    const colDefs = ref(null);
    const defaultColDef = ref({
      filter: "agTextColumnFilter",
      floatingFilter: true,
      sortable: true,
      resizable: false,
      editable: true,
      flex: 1,
    });
    const onGridReady = (params) => {
      gridApi.value = params.api;
    };
    onBeforeMount(() => {
      rowData.value = RowData.value;
      colDefs.value = colData.value;
      rowSelection.value = "multiple";
      paginationPageSize.value = 25;
      paginationPageSizeSelector.value = [25, 50, 75];
    });
    return {
      rowData,
      colDefs,
      defaultColDef,
      paginationPageSize,
      paginationPageSizeSelector,
      onGridReady,
    };
  },
};
</script>
<style lang="scss">
@import "@ifxglobal/vue-cli-plugin-grid-theme/gridTheme.scss";

.header {
  font: $ifxHeadingHeading04;
}
.ag-grid-container {
  margin-top: -7.5px;
  height: calc(100vh - 89px);
}
</style>
