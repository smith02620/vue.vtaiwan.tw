<template lang="jade">
#app.app
  Navbar.navbar(:routes = "myRoutes", :allTopics = "allTopics")

  #main.main
    transition(name='fade-out-speard-in', mode='out-in')
      router-view.view(:allTopics="allTopics", :catagories="catagories")

  MyFooter.footer
</template>

<script>

import Navbar from './components/app_Navbar.vue'
import MyFooter from './components/MyFooter.vue'

export default {
  components: {
    Navbar,
    MyFooter
  },
  data () {
    return {
      myRoutes: [
        {en:'Home',t:'首頁',r:''},
        {en:'User manual',t:'使用手冊',r:'how-to-use'},
        {en:'About',t:'關於 vTaiwan',r:'intro'},
        {en:'Login', t:'登入',r:'login'},
      ],
      catagories: [
        {t: '科技', routeName: 'technology'},
        {t: '文化', routeName: 'culture'},
        {t: '教育', routeName: 'education'},
        {t: '勞動', routeName: 'labor'},
        {t: '社會', routeName: 'social_policy'},
        {t: '農業', routeName: 'agriculture'},
        {t: '工業', routeName: 'industry'},
        {t: '商業', routeName: 'commerce'},
        {t: '生態', routeName: 'ecology'},
        {t: '經濟', routeName: 'economy'},
        {t: '財稅', routeName: 'tax'},
        {t: '交通', routeName: 'transport'},
        {t: '健康', routeName: 'health_care'},
        {t: '體育', routeName: 'sports', 
          cover: 'http://lorempixel.com/320/240/sports'},
      ],
      allTopics: [
        {   slogan:'邁向世界的舞台', 
            routeName: 'english_company_name',
            title:'公司英文名稱登記', 
            status:'討論中',
            progress: 10,
            total: 30,
            owner: '內政部',
            catas: ['科技','文化'],
            cover:'http://static.thousandwonders.net/Taiwan.original.3738.jpg',
            likes: 7569
        },        
        {   slogan:'理想與現實',
            routeName: 'social_enterprise_company_law',
            title:'公司法中的社會企業',
            status:'討論中',
            progress: 24,
            total: 30,
            owner: '經濟部',
            catas: ['經濟','文化'],
            cover:'http://lorempixel.com/320/240/transport',
            likes: 4543
        },        
        {   slogan: '事做不夠假放不夠',
            routeName: 'labor_vacation_draft',
            title:'一例一休草案', 
            status:'已送審', 
            progress: 6,
            total: 30,
            owner: '勞動部',
            catas: ['社會','工業','文化'],
            cover:'http://lorempixel.com/320/240/sports',
            likes: 2543
        },        
        {   slogan: '那一天，遠方辦公',
            routeName: 'labor_vacation_draft',
            title:'那一天，遠方辦公', 
            status:'已送審', 
            progress: 24,
            total: 30,
            owner: '勞動部',
            catas: ['社會','工業','文化'],
            cover:'http://lorempixel.com/320/240/sports',
            likes: 2543
        },        
        {   slogan: '那一天，遠方辦公',
            routeName: 'labor_vacation_draft',
            title:'那一天，遠方辦公', 
            status:'已送審', 
            progress: 24,
            total: 30,
            owner: '勞動部',
            catas: ['社會','工業','文化'],
            cover:'http://lorempixel.com/320/240/sports',
            likes: 2543
        },        
        {   slogan:'那一天，遠方辦公',
            routeName: 'test0',
            title:'那一天，遠方辦公', 
            status:'已送審', 
            progress: 24,
            total: 30,
            owner: '不管部',
            catas: ['教育','文化'],
            cover: 'http://lorempixel.com/320/240/sports',
            likes: 143
        },        
        {   slogan:'談場戀愛吧',
            routeName: 'test1',
            title:'談場戀愛吧', 
            status:'已送審', 
            progress: 24,
            total: 30,
            owner: '不管部',
            catas: ['教育','文化'],
            cover: 'http://lorempixel.com/320/240/sports',
            likes: 143
        },        
        {   slogan:'發達起來',
            routeName: 'test2',
            title:'發達起來', 
            status:'已送審', 
            progress: 24,
            total: 30,
            owner: '不管部',
            catas: ['教育','文化'],
            cover: 'http://lorempixel.com/320/240/sports',
            likes: 143
        },        
        {   slogan:'發達起來',
            routeName: 'test2',
            title:'發達起來', 
            status:'已送審', 
            progress: 24,
            total: 30,
            owner: '不管部',
            catas: ['教育','文化'],
            cover: 'http://lorempixel.com/320/240/sports',
            likes: 143
        },        
        {   slogan:'發達起來',
            routeName: 'test2',
            title:'發達起來', 
            status:'已送審', 
            progress: 24,
            total: 30,
            owner: '不管部',
            catas: ['教育','文化'],
            cover: 'http://lorempixel.com/320/240/sports',
            likes: 143
        }
      ]
    }
  },
  methods: {
    pure(path) {
      var obj = this.myRoutes.filter((o) => {
        return '/'+o.r == path;
      })[0]
      return obj ? obj.r : ''
    }
  }
}

</script>

<style lang="scss">

@import "./sass/global.scss";

* {  box-sizing: border-box }
a, button {
  cursor: pointer !important;
}

html {
  font-size: 16px;
  font-size: 2.5vm;
  font-size: 2.5vmin;
}

body {
  visibility: visible;
  opacity: 1;
  @include transition(opacity 0.5s ease);
  padding: 0;
  margin: 0;
}

strong {
  font-weight: 900;
  color: black;
}

</style>

<style lang="scss" scoped>

@import "./sass/global.scss";

.app {
  min-height: 100vh;
  width: 100%;
  margin: 0;
  @include transition(border-color 0.5s ease);
  &.join {    border-color: $join  }
  &.intro {    border-color: $intro  }
  &.live {    border-color: $live  }
  &.track {   border-color: $track  }
}

.main {
  position: relative;
  top: 0;
  width: 100%;
  text-align: center;
}


.fade-out-speard-in-enter, .fade-out-speard-in-leave-active {
  opacity: 0
}

.fade-out-speard-in-leave-active {
  // @include transition(all .3s);
}

.fade-out-speard-in-enter-active {
  @include transition(all .5s ease-in);
}

.fade-out-speard-in-enter {
  @include transform(rotateY(45deg));
}

.navbar {
  position: fixed;
  z-index: 50000;
  top: 0;
  left: 0;
  right: 0;
}

.footer {
  position: relative;
  margin: 0 auto;
  margin-top: 40px;
  max-width: 1170px;
}

</style>
