<template>
<div>
  <div class="item-home" v-for="item in qs">
    <div class="number-value">{{item.value}}</div>
    <div class="title">{{item.title}}</div>
    <div class="number-ans"> هنالك {{item.ans}} إجابات على هذا السؤال</div>
  </div>
</div>
</template>

<script>
export default {
  name: "home",
  data: function() {
    return {
       items: [
      { message: 'Foo' },
      { message: 'Bar' }
    ],
      qs: [
        {
          id: 1,
          title: "السؤال الأول في الموقع الجديد",
          value: 2,
          ans: 6
        },
        {
          id: 1,
          title: "السؤال الثاني في الموقع الجديد",
          value: 5,
          ans: 4
        }
      ]
    };
  },
  created: function() {},
  methods: {
    drop: function(x) {
      axios.get("http://localhost/BlogApi/drop.php?id=" + x).then(res => {
        this.check = res.data;
        axios.get("http://localhost/BlogApi/Posts.php").then(res => {
          this.post = res.data;
        });
      });
    }
  }
};
</script>

<style  lang="scss">
.item-home {
  float: right;
  width: calc(100% - 2px);
  height: 120px;
  border: 1px solid #eee;
  margin-bottom: 20px;
  .number-value{
    float: right;
    width: 120px;
    height: 120px;
    line-height: 120px;
    background: #3498db;
    color:#fff;
    text-align: center;
    font-size: 40px;
  }
  .title{
    float: right;
    width: calc(100% - 120px);
    height: 70px;
    line-height: 70px;
    font-size: 32px;
    text-align: center;
    border-bottom: 1px solid #eee;
    color: #d35400;
  }
  .number-ans{
    float: right;
    width: calc(100% - 120px);
    height: 49px;
    line-height: 49px;
    color: #666;
    text-align: center;

  }
}
</style>

