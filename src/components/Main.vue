<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
  </div>

  <div class="vote-wrapper">
    <Vote username="My User" />
  </div>

    <Results :poolResult="poolResultData"/>

</template>

<script>

import Vote from './Vote';
import Results from './Results';

export default {
  name: 'Main',
  components:{Vote, Results},
  data(){
    return {
      poolResultData:[
        {'question':'Hast du haustiere ?',
        'answer':'Ja',
        'valueProcent':56},
        {'question':'Hast du haustiere ?',
        'answer':'Nein',
        'valueProcent':44}
      ]}
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang ="scss" scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

/*
* My Styles
*/

.vote-wrapper{
  min-width: 300px;
  max-width: 500px;
  min-height: 300px;
  max-height: 800px;
  margin:auto;
}


</style>
