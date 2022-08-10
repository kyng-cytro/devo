<template>
  <div class="ne-item">
    <div style="display: flex">
      <div class="thumbnail">
        <div class="image-container">
          <img :src="item.image" :srcset="`${item.image}&dpr=2 2x`" width="80" height="80" />
        </div>
      </div>
      <div class="serie-info">
        <div class="title-row">
          <a  :href="item.link"> {{ formatTitle(item.name) }}</a>
        </div>
        <h3 class="description">
          {{ item.summary }}
        </h3>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Row',
  props: {
    item: {
      required: true,
      type: Object,
    },
  },
  methods: {
    formatTitle(title) {
      return title.replace(/\s+/g, ' ').slice(0, 40);
    },
  },
};
</script>

<style scoped>
.ne-item {
  font-size: 16px;
  padding: 16px 0;
  text-align: left;
  border-bottom: 1px solid #dfe3e8a8;
}

.night-mode .ne-item {
  border-bottom: 1px solid #dfe3e82d;
}

.ne-item a {
  text-decoration: none;
  color: inherit;
}

.ne-item .thumbnail {
  width: 80px;
  height: 80px;
  margin-right: 8px;
}

.ne-item .image-container {
  width: 80px;
  height: 80px;
}

.ne-item a:hover {
  text-decoration: underline;
  text-decoration-line: underline;
  text-decoration-style: initial;
  text-decoration-color: initial;
}

.ne-item .title-row {
  font-size: 20px;
  font-weight: 300;
  line-height: 32px;
}

.ne-item .description {
  align-items: center;
  color: rgb(153, 153, 153);
  font-size: 13px;
  font-weight: 400;
  line-height: 20px;
  margin-bottom: 5px;
  margin-top: 0px;
}

.serie-info {
  flex: 1;
  padding-left: 0.5rem;
}
.truncate {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>
