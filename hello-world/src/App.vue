<template>
  <div>{{ greet }} {{ name }}</div>
  <div v-text="channel"></div>
  <div v-html="hack"></div>
  <h2 :id="headingId">Heading</h2>
  <button :disabled="isDisabled">Bind</button>
  <h2 class="underline">Underline text</h2>
  <h2 class="uderline" :class="status">Status</h2>
  <h2 :class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h2 :class="isSoldout ? 'sold-out' : 'new'">Soldout? movie</h2>
  <h2 :class="['new', 'promoted']">Newly promoted movie</h2>
  <h2 :class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">Array conditional movie</h2>
  <h2 :class="{
    promoted: isPromoted,
    new: !isSoldout,
    'sold-out': isSoldout
  }">Object conditional movie</h2>
  <h2 :style="{
    color: highlightColor,
    fontSize: headerSize + 'px',
    padding: '20px' 
    }">Inline Style</h2>
  <h2 :style="headerStyleObject">Style Object</h2>
  <div :style="[baseStyleObject, successStyleObject]">Success Style</div>
  <div :style="[baseStyleObject, dangerStyleObject]">Danger Style</div>
  <h2 v-if="num === 0">The number is zero</h2>
  <h2 v-else-if="num < 0">The number is negative</h2>
  <h2 v-else-if="num > 0">The number is positive</h2>
  <h2 v-else>Not a number</h2>
  <template v-if="display">
    <h2>Engr. Leonel J. Felezario</h2>
    <h2>Hotdog</h2>
    <h2>Vue</h2>
  </template>
  <h2 v-show="showElement">Using v-show</h2>
  <h2 v-if="showElement">Using v-if</h2>
  <h2 v-for="(name, index) in names" :key="name">{{ index }} {{ name }}</h2>
  <h2 v-for="name in fullNames" :key="name.first">{{ name.first }} {{ name.last }}</h2>
  <div v-for="actor in actors" :key="actor.name">
    <h2>{{ actor.name }}</h2>
    <h3 v-for="movie in actor.movies" :key="movie">{{ movie }}</h3>
  </div>
  <h2 v-for="(value, key, index) in myInfo" :key="value">{{ index }} {{ key }} {{ value }}</h2>
  <template v-for="name in names" :key="name">
    <h2>{{ name }}</h2>
    <hr />
  </template>
  <template v-for="name in names" :key="name">
    <h2 v-if="name === 'Bruce'">{{ name }}</h2>
  </template>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      greet: "Hello",
      name: "Engr. Leonel J. Felezario",
      channel: "Hotdog",
      hack: `<a href="#" onclick="alert('All your base are belong to us!')">CLICK ME!<a/>`,
      headingId: 'heading',
      isDisabled: true,
      status:'danger',
      isPromoted: true,
      isSoldout: true,
      highlightColor: "orange",
      headerSize: 50,
      headerStyleObject: {
        color: 'orange',
        fontSize: '50px',
        padding: '20px'
      },
      baseStyleObject: {
        fontSize: '50px',
        padding: '10px',
      },
      successStyleObject: {
        color: 'green',
        backgroundColor: 'lightgreen',
        border: '1px solid green',
        padding: '20px',
      },
      dangerStyleObject: {
        color: 'darkred',
        backgroundColor: 'red',
        border: '1px solid darkred',
      },
      num: "Hi",
      display: true,
      showElement: false,
      names: ['Bruce', 'Clark', 'Diana'],
      fullNames: [
        { first: 'Bruce', last: 'Wayne'},
        { first: 'Clark', last: 'Kent'},
        { first: 'Princess', last: 'Diana'},
      ],
      actors: [
        {
          name: 'Christian Bale',
          movies: ['Batman', 'The Prestige'],
        },
        {
          name: 'Di Caprio',
          movies: ['Titanic', 'Inception']
        },
      ],
      myInfo: {
        name: 'Leonel',
        channel: 'Hotdog',
      }
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}

.new {
  color: olivedrab;
}

.sold-out {
  color: red;
}
</style>
