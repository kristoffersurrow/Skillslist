<template>
    <div id="template">
        <h1>{{message}}</h1>
        <div class="spacer"></div>

    <div class="interpolation">
        <!-- Vue Interpolation -->
        {{name}}

        <br/><br/>
        <!-- eventhandling -->
        <button v-on:click="clickMe">ClickMe</button>
        <br/><br/>

        <!-- Vue function interpolation -->
        <!-- Vue directories -->
        <button v-bind:disabled="btnState">{{btnState ? 'The button is disabled' : 'The button is active'}}</button>

    </div>
    <br/>
    <div class="stylebinding">
        <!-- Class binding - bind alert class if showAlert is true, if show it when false use !showAlert -->
        <div class="notAlert" v-bind:class="{alert:showAlert}">
        
        <!-- Her defineres et object med "klasser" og objektet bindes som klasse -->
        <!-- <div v-bind:class="alertObject"> -->

        </div>

    </div>
    <div class="loops">
        <div class="holder">
            <ul>
                <!-- Iterating through an array -->
                <li v-for="(data,index) in skills" v-bind:key="index"> {{data.skill}} </li>
            </ul>

            <!-- Conditionals -->
            <p v-if="skills.length >= 1">You have more than 1 skill</p>
            <p v-else>You have less than, or equal to 1 skill</p>
        
        </div>
    </div>
    <div class="spacer"></div>
    <div class="spacer"></div>

    <div class="skillList">
        <!-- Her indsættes SkillList Component -->
       <SkillList/> 
    </div>

    </div>
</template>


<script>
import SkillList from './SkillList.vue'

export default {
    name:"Skills",
    components:{
        SkillList
    },
    props: {
        message : String
    },
    methods: {
        clickMe() {
            this.btnState = !this.btnState;
            this.showAlert = !this.showAlert;
        }
    },
    data() {
       return {
           name: 'Skills',
           btnState:true,
           skills: [
               { skill : "Vue"},
               { skill : "Angular"},
               { skill : "React"},
               { skill : "Frontend developer"}
           ],
           showAlert:true,
        }
    }
}

</script>


<style scoped>
.notAlert{
    background-color: blue;
    width: 250px;
    height: 50px;
}

.alert{
    background-color: red;

}
button {
    padding: 10px;
}

</style>



