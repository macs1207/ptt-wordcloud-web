<template>
  <a-layout>
      <a-layout-header>
        <div>
          <a-row>
            <a-col :span="4">
              CUSTOM ICON
            </a-col>
            <a-col :span="10">
              <a-select default-value="選擇PTT看版" style="width: 100%" @change="selectBoard">
                <a-select-option v-for="(board, index) in pttBoard" :key="index" :value="board">
                  {{board}}
                </a-select-option>
              </a-select>
            </a-col>
          </a-row>
        </div>
      </a-layout-header>
      <a-layout-content>
        <a-card v-for="(articleInfo, index) in boardArticle[selBoard]" :key="index" :title="articleInfo.title">
          <a-button-group slot="extra">
            <a-button type="primary" disabled="true"><a-icon type="like" />100</a-button>
            <a-button type="danger" disabled="true"><a-icon type="dislike" />0</a-button>
          </a-button-group>
          <a-button slot="extra" href="#">Generate</a-button>
          <a-button slot="extra" href="#">View</a-button>
          <a-button slot="extra" type="link" href="#">Link</a-button>
        </a-card>
      </a-layout-content>
    </a-layout>
</template>

<script>
export default {
  name: 'Home',
  methods: {
    selectBoard (board) {
      this.selBoard = board
    }
  },
  data () {
    return {
      selBoard: '',
      pttBoard: ['Marvel', 'Stock'],
      boardArticle: {
        Marvel: [
          { title: 'MT1', id: 't1', link: '/T1' },
          { title: 'MT2', id: 't2', link: '/T2' },
          { title: 'MT3', id: 't3', link: '/T3' },
          { title: 'MT4', id: 't4', link: '/T4' },
          { title: 'MT5', id: 't5', link: '/T5' }
        ],
        Stock: [
          { title: 'T1', id: 't1', link: '/T1' },
          { title: 'T2', id: 't2', link: '/T2' },
          { title: 'T3', id: 't3', link: '/T3' },
          { title: 'T4', id: 't4', link: '/T4' },
          { title: 'T5', id: 't5', link: '/T5' }
        ]
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
