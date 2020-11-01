<template>
    <div class="vote-window__main" @click ="favoriteTwoot(twoot.id)">
        <div class="vote-window__question-label">
            <p>Zeit fur noch eine Frage? </p>
            <p>{{poolResult[0].answer}}</p>
            <p>{{poolResult[0].valueProcent + 0.1}}</p>
            
        </div>
        <v-alert type="success"></v-alert>

        <v-banner elevation="15" single-line :sticky="sticky">
            We can't save your edits while you are in offline mode.

            <template v-slot:actions>
                <v-btn
                text
                color="deep-purple accent-4"
                >
                Get Online
                </v-btn>
            </template>
    </v-banner>

    <v-btn depressed color="primary"> Primary </v-btn>


    </div>
</template>


<script>
export default {
    name:"Results",
    props:{
        poolResult:{
            type: Object,
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

            &:hover{
                transform: scale(1.1,1.1);
            }
        }
    }

}

</style>