<template>
    <div id="section">    
        <div class="loops">
        <div class="holder">
            
            <!-- Eventhandler kaldes ved submit -->
            <form @submit.prevent="addSkill">
                <!-- v-model sætter skill lig input i textfeltet -->
            <input type="text" placeholder="Indtast en Vue-skill du har.." v-model="skill"/>
            </form>

            <ul>
                <transition-group name="list" enter-active-class="animated bounceInUp" leave-active-class="animated bounceOutDown">
                <!-- Iterating through an array -->
                <li v-for="(data,index) in skills" v-bind:key="index"> {{data.skill}} </li>
                </transition-group>
            </ul>

            <p>Dette er mine Vue skills</p>
        </div>
        </div>
    </div>
</template>


<script>
export default {
    name:"SkillList",
    data() {
       return {
           skill: '',
           skills: [
               { skill : "Interpolation"},
               { skill : "Directives"},
               { skill : "Conditionals"},
               { skill : "Loops"},
               { skill : "Class binding"}
           ],
        }
    },
    methods: {
        addSkill() {
            this.skills.push({skill:this.skill})
            this.skill = '';
        }
    }
}

</script>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=Montserrat:400,700');
@import "https://cdn.jsdelivr.net/npm/animate.css@3.5.1";

#section{
    font-family: 'Montserrat', sans-serif;
    padding: 50px;
    width: 50%;
}

.holder {
    background: #fff;
  }

  ul {
    margin: 0;
    padding: 0;
    list-style-type: none;
  }
  
  ul li {
    padding: 20px;
    font-size: 1.3em;
    background-color: #E0EDF4;
    border-left: 5px solid #3EB3F6;
    margin-bottom: 2px;
    color: #3E5252;
  }

  p {
    text-align:center;
    padding: 30px 0;
    color: gray;
  }

  .container {
    box-shadow: 0px 0px 40px lightgray;
  }

input {
    width: calc(100% - 40px);
    border: 0;
    padding: 20px;
    font-size: 1.3em;
    background-color: #323233;
    color: #687F7F;
    }

.alert-in-enter-active {
  animation: bounce-in .5s;
}
.alert-in-leave-active {
  animation: bounce-in .5s reverse;
}
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}
</style>
