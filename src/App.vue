<script>
export default {
  name: "App",
  data() {
    return {
    //   name: "Foysal",
    //   company: "BJIT Limited",
    //   id: `<a href="#" onclick>11213</a>`,
    //   headingId: 'heading',
    //   isDisabled: true,
    //   count: 1,
    //   someObject: {},
    //   obj: {
    //     nested: { count: 0 },
    //     arr: ['foo', 'bar']
    //   },
    //   textColor: 'primaryText',
    //   isActive: true,
    //   styleObject: {
    //     color: 'teal',
    //     fontSize: '28px'
    //  }

    // Conditional Rendering
      num: 5,
      displayItem: true,

    // List Rendering
      names: ['Foysal', 'Mahmud', 'Prince'],
      fullNames: [
        {first: "Foysal", last: "Mahmud"},
        {first: "Prince", last: "Mahmud"},
        {first: "Ragnar", last: "Lothbrok"},
      ],
      actors: [
        {
          name: "Christian Bale",
          movies: ['Batman', 'The Prestige']
        },
        {
          name: 'De Caprio',
          movies: ['Titanic', 'Inception']
        }
      ],
      myInfo: {
        name: 'Foysal Mahmud',
        company: "BJIT"
      }
    }
  },
  methods: {
    increment() {
      this.count++
    },
    mutateDeeply() {
      // these will work as expected.
      this.obj.nested.count++;
      this.obj.arr.push('baz');
    }
  },
  mounted() {
    // methods can be called in lifecycle hooks, or other methods!
    this.increment();

    this.mutateDeeply();

    console.log(this.count); // => 1
    this.count = 2;

    const newObject = {};
    this.someObject = newObject;

    console.log(newObject === this.someObject); // false
  }
}
</script>

<template>
  <div>
    <!-- <div> Hello {{ name }}</div>
    <div v-text="company"></div>
    <div v-html="id"></div>
    <h2 v-bind:id="headingId">Heading</h2>
    <button :disabled="isDisabled">Button</button>
    <h1>  Count is: <span style="color: blue"> {{ count }} </span></h1>
    <button @click="increment">Increment by 1</button>
    <h2>  Nested Count is: <span style="color: green"> {{ obj.nested.count }} </span></h2>
    <button @click="mutateDeeply">Increment Nested count</button>
    <p v-bind:class="textColor">Primary Text color</p>
    <h2 v-bind:class="isActive && 'activeStatus'">Active Status</h2>
    <h2 v-bind:class="isActive ? 'yes' : 'no'">Is Active? yes(Blue) : No (red)</h2>
    <div :style="styleObject">Binding to Objects</div> -->
    
    <!-- Conditional Rendering -->
    <h2 v-if="num === 0">Number is Zero(0)</h2>
    <h2 v-else-if="num > 0">Number is Positive(+)</h2>
    <h2 v-else-if="num < 0">Number is Negative(-)</h2>
    <h1 v-else>Oh no 😢. NOT a Number</h1>

    <template v-if="displayItem">            
      <!-- <div v-if="displayItem"> -->
      <h3>Item 1</h3>
      <h3>Item 2</h3>
      <h3>Item 3</h3>
    </template> 

    <h2 v-show="displayItem">Using v-show </h2>

    <!-- List Rendering -->
    <h3 v-for="name in names" :key="name">{{ name }}</h3>
    <h5 v-for="(name, index) in names" :key="name">Person {{index}}: {{ name }}</h5>

    <h2 v-for="name in fullNames" :key="name.first">{{ name.first }} {{ name.last }}</h2>

    <div v-for="actor in actors" :key="actor.name">
      <h1>{{ actor.name }}</h1>
      <h3 v-for="movie in actor.movies" :key="movie">{{ movie }}</h3>
    </div>

    <h2 v-for="(value, key, index) in myInfo" :key="value">{{ index }} {{ key }} {{ value }}</h2>

    <template v-for="name in names" :key="name">
      <h2 v-if="name === 'Foysal'">{{ name }}</h2>
    </template>
  </div>
</template>

<style>
#app {
  background-color: #f2f2f2; /* Gray background color */
  width: 100vw;
  height: 100vh; /* Set the height to fill the viewport */
  color: black;
}

.primaryText {
  color: orchid;
  font-size: 24px;
  font-weight: bold;
}

.activeStatus {
  color: #308b02;
  font-style: italic;
}

.yes {
  color: blue;
}

.no {
  color: red;
}

</style>

