<template>
    <div class="home">
        <ul>

            <li v-for="(item,index) in conponentArr">{{item.name}}</li>
        </ul>
        <div style="margin: 0 auto; width: 100%; text-align: center">
          <component :is="isconponent"></component>
        </div>
    </div>
</template>

<script>
    // @ is an alias to /src
    import Countto from '../components/count-to'

    export default {
        name: 'Home',
        data() {
            return {
                conponentArr: [
                    {name: '倒计时', value: 'Countto'}
                ],
                isconponent: 'Countto'
            }
        },
        components: {
            Countto
        }

    }
</script>
<style>
    ul, li {
        list-style: none;

    }
  .home ul{
    width:200px; text-align: center; height: 600px; box-shadow:0px 1px 6px 4px rgba(242,242,242,1);
  }
    .home li{
      padding: 15px 0 ; cursor: pointer; border-bottom: 1px solid #cccccc;
    }
</style>
