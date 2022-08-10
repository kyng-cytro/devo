<template>
  <div class="ne-list">
    <row v-for="(item, index) in lines" :key="index" :item="item"></row>
  </div>
</template>

<script>
import { mapState } from 'vuex';
import Row from '@/components/NextEpisode/Row.vue';

export default {
  name: 'Body',
  components: { Row },
  computed: {
    ...mapState({
      lines: state => state.nextepisode.data,
    }),
  },
};
</script>
<style>
.ne-list > :last-child {
  border: none;
}
</style>
