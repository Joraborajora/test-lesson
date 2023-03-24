<!-- <script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style> -->


<script>



export default {
  data() {
    return {
      par1: 'first text level',
      par2: 'single text level',
      par3: 'three text level',
      visible: true,
      visible1: true,
      visible2: true,
      visible3: true;
      num: 5,
      num1: 1,
      num2: 2,
      num3: 3,
      name: 'Jon',
      sur: 'Smith',
      // text1: '111',
      // text2: '222',
      text: 'page',
      href: 'page.html',
      arr: ['x','y','z'],
      arr1: [1,2,5],
      obj: {x:2, y:4, z:1},
      cost: 25,
      amount: 4
    }
  },
//   methods: {
// 	show: function() {
// 		let dat = this.cape();
// 		alert(dat);
// 	},
// 	cape: function() {
//     return new Date().toDateString();
// 		// return str[0].toUpperCase() + str.slice(1);
// 	}
// }
// methods: {
// show: function() {
// // alert(new Date().toDateString());
// // alert('твой день'+this.num1+this.num2)
// let text = this.cape(this.text);
// }

// cape: function(str) {
//  return str[0].toUpperCase() + str.slice(1); 
// }
// }

methods: {
  toggle1: function(){
this.visible3 = !this.visible3;
  },
  toggle: function() {
	this.visible2 = !this.visible2;
}, 
  hide: function(){
        this.visible1 =  !this.visible1;
      },
    
  show: function(str) {
    alert(str);
  },

  real: function(num) {
    alert(num*num);
  },

  change: function(){
    this.text = 'balbous';
  },
  change1: function(){
    this.name = "Gocha";
  },
  change2: function() {
    this.cost = 10;
  }
},
computed: {
  full: function() {
    return this.name+' '+this.sur;
  },
  price: function() {

    let sum = this.cost * this.amount;
    return sum;
  }
}
}
</script>

<template>
 

  <!-- {{ show() }} -->

 <div> {{ name }}</div>
  <div>{{ sur }}</div>
  <p><a :href="href" >{{ text }}</a></p><br>
  <p>{{ num*num }}</p>
  <p>{{ num1+num2+num3 }}</p>
  <p>{{ arr[0] }}</p>
  <p>{{ arr[1] }}</p>
  <p>{{ arr[2] }}</p>
  <p>{{ arr1[0]+arr1[1]+arr1[2] }}</p>
  <p>{{ obj.x+obj.y+obj.z }}</p>
  <div>
    Hello World!
  </div><br>
  <p v-if="visible">Welcome!</p>
  <button v-if="!visible" @mouseover="show">Data button</button>
  <button @click="show('text1')">btn1</button>
  <button @click="show('text2')">btn2</button>
  <button @click="real(2)">Sum 1</button>
  <button @click="real(3)">Sum 2</button>
   <p>{{ text }}</p> 
   <button @click="change">text</button>
   <p>{{ name }}</p>
   <button @click="change1">text</button>
   <p>{{ full }}</p>
   <p>Product: {{ price }}</p>
   <button @click="change2">New price</button>
   
   <button @click="hide">hide</button>
   <p v-if="visible1">{{ full }}</p>

   <button @click="toggle">{{ visible2 ? full : price }}</button>
	 <!-- <p v-if="visible2">text</p> -->

   <button @click="toggle1">first but</button>
   <p v-if="visible3">{{ par1 }}</p>
   <p>{{ par2 }}</p>
   <p>{{ par3 }}</p>
</template>