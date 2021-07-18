<template>
    <form class="form">
        <div class="email">
            <label for="email">Email:</label>
            <br>
            <input type="text" id="email">
        </div>

        <div class="password">
            <label for="password">Password:</label>
            <br>
            <input type="password" id="password">
        </div>

        <div class="profession">
            <label for="profession">Role:</label>
            <br>
            <select id="profession" value="">
                <option value="developer">Web Developer</option>
                <option value="designer">Web Designer</option>
            </select>
        </div>

        <div class="skills">
            <label for="skill">Skills:</label>
            <br>
            <input type="text" id="skill">
        </div>

        <div class="agree">
            <input class="check" id="check" type="checkbox"> 
            <label for="check">I agree with all your requirments</label>
        </div>

        <br>
        <button>Create an account</button>
    </form>
</template>

<script>
export default {

}
</script>

<style scoped>
    .form{
        width:500px;
        height:600px;
        padding: 50px 100px;
        justify-content: center;
        margin: auto;
        border-radius: 20px;
        background-color: white;
        font-size: 1.4em;
        border: solid rgb(160, 159, 159);
    }
    input{
        width: 500px;
        height: 40px;
        font-size: 0.7em;
        margin-bottom: 30px;
    }
    select{
        width: 500px;
        height: 40px;
        font-size: 0.7em;
        margin-bottom: 30px;
    }

    .check{
        width: 20px;
        height: 20px;
        font-size: 0.25em;
    }
    .agree{
        display: inline-block;
        width: 380px;
        height: 40px;
        font-size: 0.8em;
    }

    button{
        display: block;
        width: 190px;
        height: 60px;
        margin: 40px auto;
        border-radius: 10px;
        background-color: rgb(85, 158, 241);
        font-size: 0.8em;
        font-family: Arial, Helvetica, sans-serif;
        color: white;
    }
</style>