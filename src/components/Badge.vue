<script setup lang="ts">
  defineProps<{
    type: string
  }>()
</script>

<template>
  <FlexboxLayout :class="{
    badge: type === 'typescript',
    'badge badge__vuejs': type === 'vuejs',
    'badge badge__github': type === 'github',
    'badge badge__kingjames': type === 'kingjames'
  }">
    <StackLayout class="badge-image-wrapper">
      <Image v-if="type.includes('vuejs')" src="~/assets/vuejs.png" class="badge-image" />
      <Image v-else-if="type.includes('typescript')" src="~/assets/typescript.png" class="badge-image" />
      <Image v-else-if="type.includes('github')" src="~/assets/github.png" class="badge-image" />
      <Image v-else src="~/assets/kingjames.png" class="badge-image" />
    </StackLayout>
    <StackLayout class="badge-text">
      <Label v-if="type.includes('vuejs')" text="Vue3" height="15"/>
      <Label v-else-if="type.includes('typescript')" text="Type S." height="15"/>
      <Label v-else-if="type.includes('github')" text="Github" height="15"/>
      <Label v-else text="King J." height="15"/>
    </StackLayout>
  </FlexboxLayout>
</template>

<style scoped>
  .badge {
    width: 265px;
    margin: 0 0 0 22px;
    background: #007acc;
    border-width: 2px;
    border-color: #007acc;
  }

  .badge__vuejs {
    width: 245px;
    margin: 0;
    border-width: 2px;
    border-color: #41b883;
    background: #41b883;
  }

  .badge__github {
    background: #000000;
    border-width: 2px;
    border-color: #000000;
  }

  .badge__kingjames {
    background: #a10004;
    border-width: 2px;
    border-color: #a10004;
  }

  .badge-image-wrapper {
    background: #fff;
  }

  .badge-image {
    width:40px;
    height:40px;
    margin:18px 18px 14px 18px;
  }

  .badge-text {
    color: #fff;
    font-size: 15px;
    font-weight: bold;
    margin: 12px 0 0 15px;
  }

</style>