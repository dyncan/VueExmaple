<template>
  <div class="test">
    <input type="text" v-model="title" />
    <h1>{{title}}</h1>
    <p>{{user.firstName}}</p>
    <p v-text="user.lastName"></p>
    <p v-if="isShow">show test</p>
    <p v-else>nobody</p>
    <ul>
      <li v-for="item in items">{{item.title}}</li>
    </ul>
    <button v-on:click="greet">say hello</button><br/>
    <input type="text" v-on:keyup="presskey" v-on:keyup.enter="hitEnter"/>
    <hr/>
    <label>first name: </label><input type="text" v-model="user.firstName" />
    <label>last name: </label><input type="text" v-model="user.lastName" />
    <h1>{{fullName}}</h1>
    <h1>{{msg}}</h1>
  </div>
</template>

<script>
export default {
  name: 'test',
  props: {
    msg: {
      type: String,
      default: ''
    }
  },
  data() {
    return {
      title: 'Hello World',
      user: {
        firstName: 'Peter',
        lastName: 'Dong'
      },
      isShow: false,
      items: [
        {title: 'item one'},
        {title: 'item two'},
        {title: 'item three'}
      ]
    }
  },
  methods: {
    greet: function () {
      alert('hello');
    },
    presskey: function (e) {
      console.log(e.target.value);
    },
    hitEnter: function(){
      console.log('hit Enter');
    }
  },
  computed: {
    fullName: function(){
      return this.user.firstName+' '+this.user.lastName;
    }
  }
}



</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
