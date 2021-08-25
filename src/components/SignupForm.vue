<template>
  <form >
  <label for="email">Electronic Mail</label>
  <input type="email" required placeholder="ironman@email.com" v-model="email">

  <label for="password">password</label>
  <input type="password" required placeholder="password" v-model="password">

  <label for="">Role:</label>
  <select v-model="role">
    <option value="Web developer">Web Developer</option>
    <option value="Web Designer">Web Designer</option>
  </select>

  <div class="terms">
    <input type="checkbox" required v-model="terms">
    <label for="">Accept terms and conditions</label>
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

</style>