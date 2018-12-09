<template>
  <div>
    <div class="carousel">
      <el-carousel :interval="4000" type="card" height="200px">
        <el-carousel-item v-for="item in 6" :key="item">
          <img :src="imgUrl">
          <!-- <h3>{{ item }}</h3> -->
        </el-carousel-item>
      </el-carousel>
    </div>

    <div class="section">
      <div class="section1">
        <el-card class="box-card1">
          <div class="clearfix" slot="header">
            <span>版块1</span>
            <el-button style="float: right; padding: 3px 0" type="text">更多</el-button>
          </div>

          <div class="item text" v-for="o in 5" :key="o">
            {{ "列表内容 " + o }}
          </div>
        </el-card>
      </div>

      <div class="section2">
        <el-card class="box-card2">
          <div class="clearfix" slot="header">
            <span>版块2</span>
            <el-button style="float: right; padding: 3px 0" type="text">更多</el-button>
          </div>

          <div class="item text" v-for="o in 5" :key="o">
            {{ "列表内容 " + o }}
          </div>
        </el-card>
      </div>

      <div class="sidebar1">
        <el-card class="side-card1">
          <div class="clearfix" slot="header">
            <span>热门版面1</span>
          </div>

          <div class="item text" v-for="o in 5" :key="o">
            {{ "列表内容" + o }}
          </div>
        </el-card>
      </div>

      <div class="section3">
        <el-card class="box-card3">
          <div class="clearfix" slot="header">
            <span>版块3</span>
            <el-button style="float: right; padding: 3px 0" type="text">更多</el-button>
          </div>

          <div class="item text" v-for="o in 5" :key="o">
            {{ "列表内容 " + o }}
          </div>
        </el-card>
      </div>

      <div class="section4">
        <el-card class="box-card4">
          <div class="clearfix" slot="header">
            <span>版块4</span>
            <el-button style="float: right; padding: 3px 0" type="text">更多</el-button>
          </div>

          <div class="item text" v-for="o in 5" :key="o">
            {{ "列表内容 " + o }}
          </div>
        </el-card>
      </div>

      <div class="sidebar2">
        <el-card class="side-card2">
          <div class="clearfix" slot="header">
            <span>热门版面2</span>
          </div>

          <div class="item text" v-for="o in 5" :key="o">
            {{ "列表内容" + o }}
          </div>
        </el-card>
      </div>

      <div class="section5">
        <el-card class="box-card5">
          <div class="clearfix" slot="header">
            <span>版块5</span>
            <el-button style="float: right; padding: 3px 0" type="text">更多</el-button>
          </div>

          <div class="item text" v-for="o in 5" :key="o">
            {{ "列表内容 " + o }}
          </div>
        </el-card>
      </div>

      <div class="section6">
        <el-card class="box-card6">
          <div class="clearfix" slot="header">
            <span>版块6</span>
            <el-button style="float: right; padding: 3px 0" type="text">更多</el-button>
          </div>

          <div class="item text" v-for="o in 5" :key="o">
            {{ "列表内容 " + o }}
          </div>
        </el-card>
      </div>

      <div class="sidebar3">
        <el-card class="side-card3">
          <div class="clearfix" slot="header">
            <span>热门版面3</span>
          </div>

          <div class="item text" v-for="o in 5" :key="o">
            {{ "列表内容" + o }}
          </div>
        </el-card>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'homepage',
  data(){
    return{
      imgUrl:''
    }
  },
  created:function(){
    this.changeimgUrl()
  },
  methods:{
    changeimgUrl(){
      // console.log(this)
      // this.imgUrl='http://turbulent.cn:5000/images/a.jpg'
      // return  this.imgUrl
      this.$axios.get('http://turbulent.cn:5000/test')
        .then( (response) =>{
            console.log(response);
            })
        .catch((error)=> {
          console.log(error);
            })
    }
  }
}

</script>

<style>

.el-carousel__item h3 {
  color: #475669;
  font-size: 14px;
  opacity: 0.75;
  line-height: 200px;
  margin: 0;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n+1) {
  background-color: #d3dce6;
}

.text {
  font-size: 14px;
}

span {
  font-size: 18px;
}

.item {
  margin-bottom: 18px;
}

.clearfix:before,
.clearfix:after {
  display: table;
  content: "";
}

.clearfix:after {
  clear: both
}

.box-card1,
.box-card2,
.box-card3,
.box-card4,
.box-card5,
.box-card6 {
  width: 90%;
  border-top-style: solid;
  border-top-width: 0.3em;

}

.box-card1 {
  border-top-color: orange;
}

.box-card2 {
  border-top-color: green;
}

.box-card3 {
  border-top-color: blueviolet;
}

.box-card4 {
  border-top-color: sienna;
}

.box-card5 {
  border-top-color: rosybrown;
}

.box-card6 {
  border-top-color: indigo;
}

.section1,
.section2,
.section3,
.section4,
.section5,
.section6 {
  width: 40%;
}

.section1 {
  float: left;
}

.section2 {
  float: left;
}

.section3,
.section4,
.section5,
.section6 {
  margin-top: 3em;
  float: left;
}

.sidebar2,
.sidebar3 {
  margin-top: 3.3em;
}

.side-card1,
.side-card2,
.side-card3 {
  border-top-style: solid;
  border-top-width: 0.3em;
  border-top-color: gray;
}
</style>
