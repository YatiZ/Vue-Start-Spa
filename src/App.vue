<template>
  <nav-bar-view :pages="pages" :activePage="activePage" :nav-link-click="(index) => activePage = index"></nav-bar-view>
  
  <page-view :page="pages[activePage]"></page-view>
  <h1>Hello World</h1>
</template>

<script>
import PageView from './components/PageView.vue';
import NavBarView from './components/NavBar.vue';
export default{
  components:{NavBarView,PageView},
  data() {
                return {
                    theme1: '',
                    useDarkNav: true,
                    activePage:0,
                    pages:[
                        {
                            link: {text:'Home',url:'home.html'},
                            pageTitle:'Home Page',
                            content:'This is Home page'
                        },
                        {
                            link: {text:'About',url:'about.html'},
                            pageTitle:'About Page',
                            content:'This is about page'
                        },
                        {
                            link: {text:'contact',url:'contact.html'},
                            pageTitle:'Contact Page',
                            content:'This is contact page'
                        },
                        
                    ]
                }
            },
}
</script>
