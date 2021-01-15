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
      <a-layout-content style="background: #FFFFFF;">
        <a-col :span="2"></a-col>
        <a-col :span="20">
          <a-card v-for="(articleInfo, index) in boardArticle[selBoard]" :key="index" :title="articleInfo.title">
            <a-button-group slot="extra">
              <a-button v-if="articleInfo.comment >= 0" disabled="true" style="width: 100px; background: #0275d8; color: #000000;"><a-icon type="like" />{{ articleInfo.comment }}</a-button>
              <a-button v-else disabled="true" style="width: 100px; background: #d9534f; color: #000000;"><a-icon type="dislike" />{{ articleInfo.comment * -1 }}</a-button>
              <a-button href="#">Generate</a-button>
              <a-button href="#">View</a-button>
              <a-button type="link" href="#">Link</a-button>
            </a-button-group>
          </a-card>
        </a-col>
        <a-col :span="2"></a-col>
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
          { title: 'MT1', id: 't1', link: '/T1', comment: 100 },
          { title: 'MT2', id: 't2', link: '/T2', comment: 10 },
          { title: 'MT3', id: 't3', link: '/T3', comment: -10 },
          { title: 'MT4', id: 't4', link: '/T4', comment: 40 },
          { title: 'MT5', id: 't5', link: '/T5', comment: -100 }
        ],
        Stock: [
          { title: 'T1', id: 't1', link: '/T1', comment: 0 },
          { title: 'T2', id: 't2', link: '/T2', comment: 20 },
          { title: 'T3', id: 't3', link: '/T3', comment: 80 },
          { title: 'T4', id: 't4', link: '/T4', comment: -10 },
          { title: 'T5', id: 't5', link: '/T5', comment: -10 }
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
