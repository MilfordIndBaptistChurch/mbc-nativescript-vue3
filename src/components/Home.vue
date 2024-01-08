<script lang="ts" setup>
  import Badge from './Badge.vue';
</script>

<template>
  <Frame>
    <Page>
      <ActionBar title="Milford Bible Companion">
        <NavigationButton text="Go back" icon="~/assets/typescript.png"></NavigationButton>
        <ActionItem icon="~/assets/hamburger.png" @tap="onToggle" ios.position="right"></ActionItem>
      </ActionBar>

      <GridLayout class="content" rows="*">
        <StackLayout>
          <Label class="title" text="Milford Bible Companion" height="35"/>
          <Label class="sub-title" text="By Milford Ind. Baptist Church" height="27"/>
          <FlexboxLayout alignItems="flex-start">
            <Badge type="vuejs" />
            <Badge type="typescript" />
            <Badge type="github" />
            <Badge type="kingjames" />
          </FlexboxLayout>
        </StackLayout>

        <ListView
          v-if="showList"
          :items="items"
          separatorColor="transparent"
          class="list"
        >
          <template #default="{ item }">
            <GridLayout columns="*, auto" class="px-4">
              <Label :text="item" class="text-lg py-3 text-black" />
            </GridLayout>
          </template>
        </ListView>
      </GridLayout>
    </Page>
  </Frame>
</template>

<script lang="ts">
  import { ref } from 'vue';

  const items = [
    'Books (5)',
    'Cross ref (6)',
    'Accordance (0)',
    'Sermons (0)',
    'Illustrations (0)',
    'Characters (4)',
    'Images (0)',
    'Bible Studies (0)',
    'Reading list (0)',
    'Notes (0)'
  ];

  const showList = ref(false);

  export default {
    methods: {
      onToggle() {
        showList.value = !showList.value;
      }
    }
  }
</script>

<style>
  .content {
    margin: 0 0 0 40px;
  }
  .title {
    font-size: 20px;
    font-weight: bold;
    margin: 25px 0 0 0;
  }
  .sub-title {
    font-size: 16px;
    margin: 0 0 25px 0;
  }
  .list {
    margin: 50px 0 0 0;
  }
</style>
