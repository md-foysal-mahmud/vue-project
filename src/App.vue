<script>
import CreatePost from './components/CreatePost.vue';
import PostList from './components/PostList.vue';
import NameList from './components/NameList.vue';
import Card from './components/Card.vue';
import Input from './components/Input.vue';
import ComponentE from './components/ComponentE.vue';
import Popup from './components/Popup.vue';
import ComponentPropsPractices from './components/ComponentPropsPractices.vue';
import Article from './components/Article.vue';
import EventHandler from './components/EventHandler.vue';
import FormHandler from './components/FormHandler.vue';
import Watchers from './components/Watchers.vue';
import BasicPractices from './components/BasicPractices.vue'

export default {
  components: {
    CreatePost,
    PostList,
    NameList,
    Card,
    Input,
    ComponentE,
    Popup,
    Article,
    ComponentPropsPractices,
    Watchers,
    FormHandler,
    EventHandler,
    BasicPractices 
  },
  name: "App",
  data() {
    return {
      // Props passing example
      name: 'Prince',
      company: 'TimTim',
      // component events
      showPopup: false,
    }
  },
  provide() {
    return {
      username: this.name
    }
  },
  methods: {
    closePopup(name) {
      this.showPopup = false;
      alert(name);
    }
  }
}
</script>

<template>
  <div>
    <h1>Create Post:</h1>
    <CreatePost />
    <br>
    <hr> 

    <h1>PostList component(Date Fetching):</h1>
    <PostList />
    <br>
    <hr> 

    <h1>Slots:</h1>
    <NameList>
      <template v-slot:default="slotProps">
        {{ slotProps.firstName }} {{ slotProps.lastName }}
      </template>
    </NameList>

     <!-- Slots -->
    <Card></Card>
    <Card>Card Content</Card>
    <Card><img src="https://picsum.photos/200" /></Card>
    <Card>
      <template v-slot:header>
        <h3>Header</h3>
      </template>
      <template v-slot:default>
        <img src="https://picsum.photos/200" />
      </template>
      <template v-slot:footer>
        <button>View Details</button>
      </template>
    </Card>

    <br>
    <hr> 
    <Input v-model="name" />

    <button @click="showPopup = true">Show Popup</button>
    <!-- <Popup v-show="showPopup" @close="showPopup = false" /> -->
    <Popup v-show="showPopup" @close="closePopup" />

    <pre>Username: {{ name }}</pre>
    <ComponentE />

    <h1>Component Props Practices:</h1>
    
    <ComponentPropsPractices name="Foysal" company="BJIT" />
    <!-- props assigned dynamically with v-bind or its : -->
    <ComponentPropsPractices :name="name" :company="company" /> 
    <Article id="article-id" title="Vikings" :likes="52" />

    <br>
    <hr> 
    
    <h1>Watchers component:</h1>
    <Watchers />

    <br>
    <hr> 
    <h1>FormHandler component:</h1>
    <FormHandler />

    <br>
    <hr> 
    <h1>EventHandler component:</h1>
    <EventHandler />

    <br><br><br>
    <hr> 
    <h1>Basic Practices:</h1>
    <BasicPractices />
  </div>
</template>

<style>
#app {
  background-color: #f2f2f2; /* Gray background color */
  width: 100%;
  height: 100%; /* Set the height to fill the viewport */
  color: black;
}
</style>

