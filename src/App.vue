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

      obj: {
        done: true,
        selected: false,
      },
     

      users: [
        {
          id: 1,
          name: 'Geo',
          surn: 'Cho',
        },{
          id: 2,
          name: 'And',
          surn: 'bog',
        },{
          id: 3,
          name: 'Ser',
          surn: 'Hir',
        },
      ],

      label: ['1','-2','-3','-4','5'],
      arr: ['you','are','bitch'],
      
      items: ['hello ','bitches ', 'mondays '],
      number: ['2','5','8'],
      obj: { a:1, b:2, c:3},
      hrefs: [
      {link: 'https://code.mu/ru/javascript/framework/vue/book/prime/loops/array-of-objects/', text: 'cat'},
      {link: '2.html', text: 'dog'},
      {link: '3.html', text: 'bird'},
      ],

      products: [
        {
          name: 'eggs',
           price: 100,
           quantity: 5
        },{
          name: 'apple',
           price: 20,
           quantity: 40
        },{
          name: 'banana',
           price: 45,
           quantity: 12 
        },
      ],
        
    
      // age: 20,
      // isAdmin: true,
      // par1: 'first text level',
      // par2: 'single text level',
      // par3: 'three text level',
      // visible: true,
      // visible1: true,
      // visible2: true,
      // visible3: true,
      // num: 5,
      // num1: 1,
      // num2: 2,
      // num3: 3,
      name: 'Jon',
      sur: 'Smith',
      hide: true,
      // text1: '111',
      // text2: '222',
      // text: 'page',
      // href: 'page.html',
      // arr: ['x','y','z'],
      // arr1: [1,2,5],
      // obj: {x:2, y:4, z:1},
      // cost: 25,
      // amount: 4
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
  toggle: function () {
   
    this.hide = !this.hide;
  },

  add: function() {
     this.arr.push( 'bitches' );
     this.arr.shift();
  }

 


//   toggle1: function() {
//   this.visible3 = !this.visible3;
//   },
//   toggle: function() {
// 	this.visible2 = !this.visible2;
// }, 
//   hide: function(){
//         this.visible1 =  !this.visible1;
//       },
    
//   show: function(str) {
//     alert(str);
//   },

//   real: function(num) {
//     alert(num*num);
//   },

//   change: function(){
//     this.text = 'balbous';
//   },
//   change1: function(){
//     this.name = "Gocha";
//   },
//   change2: function() {
//     this.cost = 10;
//   }
// },
// computed: {
//   full: function() {
//     return this.name+' '+this.sur;
//   },
//   price: function() {

//     let sum = this.cost * this.amount;
//     return sum;
//   }
}
}
</script>

<template>

  <p v-for="elem in arr">

      {{ elem }}
  
  </p>
  <button @click="add">Click here</button>


<p :class="obj" v-for="user in users" :key="user.id">
{{ user.name  }}
{{ user.surn }}
</p>

<ul>
  <template v-for="elem in label">

    <li v-if="elem > 0">

      {{ elem }}
    </li>
  </template>
 
</ul>
  

  <table>
    <tr v-for="product in products">
     
         <td>{{ product.name }}</td>
         <td>{{ product.price }}</td>
         <td>{{ product.quantity }}</td>
    
    </tr>
  </table>

<template v-for="href in hrefs">

  <ul>
    <li><a :href="href.link">{{ href.text }}</a></li>
    <hr>
  </ul>

</template>

 <p v-for="elem in arr">{{ elem }}</p>
<div v-for="elem in items">{{ elem }}</div>
 
<div v-for="elem in number">
  <ul>
    <li>
      {{ elem*elem }}
    </li>
  </ul></div>
  <div v-for="(elem, key) in number">
    {{ key+1 }} {{ elem }}
  </div>

  <template v-for="(elem,key, index) in obj">
<ul>
  <li>
    {{index+1}} - {{ key }}  - {{ elem }}
  </li>
  <hr>
</ul>
   
  </template>
  <!-- {{ show() }} -->

 <div> {{ name }}</div>
  <div>{{ sur }}</div>

<p v-if="hide">Text example</p>
<p v-show="hide">Text error</p>
<button @click="toggle">Hide or reset</button>



  <!-- <p><a :href="href" >{{ text }}</a></p><br>
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
	 


   <p >{{ visible3 ? par1 : par2 }}</p>
   <button @click="toggle1">first but</button> 
   <p>{{ par2 }}</p>
   <p>{{ par3 }}</p>

  <p v-if="isAdmin">Login</p>
  <p v-else>Unloggined</p>



  <p v-if="age>=19 && age<=25">True years</p>
  <p v-else-if="age < 19"> young babe</p>
  <p v-else-if="age > 25"> old babe</p> -->
</template>

<style>
p.selected {
  color: red;
}
</style>