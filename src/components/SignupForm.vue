<template>
  <form >
  <label for="email">Electronic Mail</label>
  <input type="email" required placeholder="ironman@email.com" v-model="email">

  <label for="password">password</label>
  <input type="password" required placeholder="password" v-model="password">
  </form>
  <p>Email: {{ email }}</p>
  <p>Password: {{ password }}</p>
</template>

<script>
export default {
    data() {
        return {
            email: '',
            password: ''
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
input {
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

</style>