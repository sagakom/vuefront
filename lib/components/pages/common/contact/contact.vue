<template>
  <vf-o-layout>
    <vf-t-common-contact :contact="contact" />
  </vf-o-layout>
</template>
<script>
import { mapGetters } from "vuex";
export default {
  head() {
    return {
      title: this.$t("pages.common.contact.metaTitle")
    };
  },
  breadcrumbs() {
    return [
      {
        title: this.$t("pages.common.contact.breadcrumbTitle"),
        to: this.$route.path
      }
    ];
  },
  computed: {
    ...mapGetters({
      contact: "common/contact/get"
    })
  },
  async fetch({ store }) {
    await store.dispatch("common/contact/get");
  }
};
</script>
