<template>
  <div id="app">
    <a-layout>
      <a-layout-header>Header</a-layout-header>
      <a-layout-content><router-view/>
        <a-button type="primary">
          Primary
        </a-button>
        <a-button>Default</a-button>
        <a-button type="dashed">
          Dashed
        </a-button>
        <a-button type="danger">
          Danger
        </a-button>
        <a-config-provider :auto-insert-space-in-button="false">
          <a-button type="primary">
            按钮
          </a-button>
        </a-config-provider>
        <a-button type="primary">
          按钮
        </a-button>
        <a-button type="link">
          Link
        </a-button>
      </a-layout-content>
      <a-layout-footer>Footer</a-layout-footer>
    </a-layout>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
</style>
