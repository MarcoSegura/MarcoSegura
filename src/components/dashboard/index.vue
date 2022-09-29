<template>
  <div class="container-fluid pt-3">
    <div
      class="container my-5"
      style="box-shadow: 1px 1px 8px #131b1e; border-radius: 15px"
    >
      <DataPrimaryUser />
    </div>
    <div class="container pt-5">
      <div
        class="row row-end d-flex align-items-center justify-content-between"
      >
        <div
          class="col-12 col-md-5"
          style="box-shadow: 1px 1px 8px #131b1e; border-radius: 15px"
        >
          <MessengerColletion />
        </div>
        <div
          class="col-12 col-md-5"
          style="box-shadow: 1px 1px 8px #131b1e; border-radius: 15px"
        >
          <ClienteVenta />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import DataPrimaryUser from "@/components/dashboard/DataPrimary/DataPrimaryUser.vue";
import MessengerColletion from "@/components/dashboard/Message/MessengerColletion.vue";
import ClienteVenta from "@/components/dashboard/SalesHistory/ClienteVenta.vue";
export default {
  name: "DashboardProducer",
  components: {
    DataPrimaryUser,
    MessengerColletion,
    ClienteVenta,
  },
  data() {
    return {};
  },
};
</script>

<style scoped>
@media (max-width: 1000px) {
  .v-application--wrap {
    background-color: none !important;
  }
}
.row-end {
  margin-bottom: 60px;
}
@media screen and (max-width: 769px) {
  .row-end {
    gap: 20px;
  }
}
a {
  flex: none;
  color: #ffffff !important;
  background-color: #333;
  border-radius: 3px;
  overflow: hidden;
  display: flex;
  flex-direction: row;
  align-content: center;
  align-items: center;
  cursor: pointer;
  margin: 0 10px 10px 0;
  text-decoration: none !important;
}
.share-network-list {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
  max-width: 1000px;
  margin: auto;
}
a[class^="share-network-"] .fah {
  background-color: rgba(0, 0, 0, 0.2);
  padding: 10px;
  flex: 0 1 auto;
}
a[class^="share-network-"] span {
  padding: 0 10px;
  flex: 1 1;
  font-weight: 500;
}
</style>
