<template>
    <v-banner elevation="6" class="vote-window__main" @click ="favoriteTwoot(twoot.id)">
        <div class="vote-window__question-label">
            <p>hast du Haustiere?</p>
        </div>
        <div class="vote-window__buttons-area">
            <button>JA, einige ...</button>
            <button>NEIN</button>
        </div>
    </v-banner>

  <div>
    <v-alert
      border="top"
      color="red lighten-2"
      dark
    >
      I'm an alert with a top border and red color
    </v-alert>
    <v-alert
      border="right"
      color="blue-grey"
      dark
    >
      I'm an alert with a right border and blue-grey color
    </v-alert>
    <v-alert
      border="bottom"
      color="pink darken-1"
      dark
    >
      I'm an alert with a bottom border and pink color
    </v-alert>
    <v-alert
      border="left"
      color="indigo"
      dark
    >
      I'm an alert with a border left type info
    </v-alert>
  </div>




</template>






<script>
export default {
    name:"Vote",
    props:{
        username:{
            type: String,
            required: true
        }
    },
    methods:{
        favoriteTwoot(id){
            this.$emit('favourite',id);
        }
    }
}
</script>

<style lang="scss" scoped>
.twoot-item{
    padding: 20px;
    background-color: white;
    border-radius: 5px;
    border : 1px solid #DFE3E8;
    box-sizing: border-box;
    cursor: pointer;
    transition: all 0.25s ease;

    &:hover{
        transform: rotate3d(1,1,1,45deg);
        transform: scale(1.1,1.1);
    }

    .twoot-item__user{
        font-weight: bold;
    }

} // end of .twoot-item



.vote-window__main{

    background-color: aquamarine;
    padding: 1px;

    .vote-window__question-label{
        background-color: aliceblue;
        opacity: 60%;
        border-radius: 10px;
        box-shadow: -10px 0px 13px -7px #000000, 10px 0px 13px -7px #000000, 5px 5px 15px 5px rgba(0,0,0,0);
        margin : 20px;
        border: 1px solid darkgray;

    }

    .vote-window__buttons-area{
        margin: 10px;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-around;
        

        button{
            width : 30%;
            max-width: 300px;
            min-width: max-content;
            padding: 10px;
            transition: all 0.3s cubic-bezier(.44,.57,.89,-0.21);

            &:hover{
                transform: scale(1.1,1.3);
                opacity: 0.7;
                border : 3px solid blueviolet;
                padding:7px;
            }
        }
    }

}

</style>