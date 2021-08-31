<template>
  <form @submit.prevent="handleSubmit">
  <label for="email">Electronic Mail</label>
  <input type="email" required placeholder="ironman@email.com" v-model="email">

  <label for="password">password</label>
  <input type="password" required placeholder="password" v-model="password">
  <div v-if="passwordError" class="error">{{ passwordError }}</div>

  <label for="">Role:</label>
  <select v-model="role">
    <option value="Web developer">Web Developer</option>
    <option value="Web Designer">Web Designer</option>
  </select>

  <label for="">Skills:</label>
  <!-- <input type="text" name="" id="" v-model="tempSkill" @keyup.alt="addSkill"> -->
  <input type="text" name="" id="" v-model="tempSkill" @keyup="addSkill">
  <div v-for="skill in skills" :key="skill" class="pill">
    <span @click="deleteSkill(skill)">{{ skill }}  X</span>
  </div>

  <div class="terms">
    <input type="checkbox" required v-model="terms">
    <label for="">Accept terms and conditions</label>
  </div>

  <div class="submit">
    <button>Create an Account</button>
  </div>


<!--
<div>
    <input type="checkbox" value="luigi" v-model="names">
    <label >Luigi</label>
</div>
<div>
    <input type="checkbox" value="yoshi" v-model="names">
    <label >Yoshi</label>
</div>
<div>
    <input type="checkbox" value="mario" v-model="names">
    <label >Mario</label>
</div>
-->


  </form>
  <p>Email: {{ email }}</p>
  <p>Password: {{ password }}</p>
  <p>Role: {{ role }}</p>
  <p>Terms: {{ terms }}</p>
  <p>TempSkill: {{ tempSkill }}</p>
  <p>Skills: {{ skills }}</p>
<!-- 
  <p>Names: {{ names }}</p>
-->
</template>

<script>
export default {
    data() {
        return {
            email: '',
            password: '',
            role: '',
            terms: false,
             // names: []
             tempSkill: '',
             skills: [],
             passwordError: ''
        }
    },
    methods: {
        //              TODO
        //-----------------------------------
        // []  Click to delete item from array
        // []  Remove the comma's from the list

        addSkill(e) {
            // console.log(e.key);
            if(e.key === ',' && this.tempSkill) {
                if(!this.skills.includes(this.tempSkill)) {
                    this.skills.push(this.tempSkill)
                }
                this.tempSkill = ''
            }
        },
        deleteSkill(skill) {
            this.skills = this.skills.filter((item) => {
                return skill !== item
            })
            // console.log(this.skills);   
        },
        handleSubmit() {
            // validate pwd
            this.passwordError = this.password.length > 5 ?
             '' : 'Password must be at least 6 characters long';

            if(!this.passwordError) {
                console.log('email: ', this.email);
                console.log('password: ',this.password);
                console.log('role: ', this.role);
                console.log('skills: ', this.skills);
                console.log('terms accepted: ', this.terms);
            }
            
        }
    }
}
</script>

<style>
form {
    max-width: 420px;
    margin: 30px auto;
    background: white;
    text-align: left;
    padding: 40px;
    border-radius: 10px;
}
label {
    color: #aaa;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: 0.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
}
input, select {
    display: block;
    padding: 10px 6px;
    width: 100%;
    border: none;
    box-sizing: border-box;
    border-bottom: #ddd;
    color: #555;
}
p {
    color: yellowgreen;
}
input[type="checkbox"] {
    display: inline-block;
    width: 16px;
    margin: 0 10px 0 0;
    position: relative;
    top: 2px;
}
.pill {
    display: inline-block;
    margin: 20px 10px 0 0;
    padding: 6px 12px;
    background: #eee;
    border-radius: 20px;
    font-size: 12px;
    letter-spacing: 1px;
    font-weight: bold;
    color: #777;
    cursor: pointer;
}
button {
    background: #0b6dff;
    border: 0;
    padding: 10px 20px;
    margin-top: 20px;
    color: white;
    border-radius: 20px;
    cursor: pointer;
}
.submit {
    text-align: center;
}
.error {
    color: #ff0062;
    margin-top: 10px;
    font-size: 0.8em;
    font-weight: bold;
}

</style>