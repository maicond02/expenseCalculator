<template>
  <div>
    <div class="container">
      <ul>
        <li v-for="page in pages" :key="pages.id">
          <a :href="page.route">{{page.name}}</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
    export default {
        data(){
            return{
              pages:[
                { id: 1,name: 'HOME', route: '/'},
                { id: 2,name: 'CALCULATOR', route: '/calculator'},
                { id: 3,name: 'ABOUT' },
              ]
            }
        }
    }
</script>

<style scoped>
  .container{
    width: 100%;
    height: 60px;
    background-color: rgb(28, 51, 177);
    display: flex;
    align-items: center;
  }
  ul li{
    list-style: none;
    display: inline;
  }
  ul li a{
    color: white;
    font-style: normal;
    text-decoration: none;
    margin-left: 10px;
  }
</style>
