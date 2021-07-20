<template>
  <form @submit.prevent="handleSubmit" class="form">
    <div class="email">
      <label for="email">Email:</label>
      <br />
      <input type="text" id="email" v-model="email" />
    </div>

    <div class="password">
      <label for="password">Password:</label>
      <br />
      <input type="password" id="password" v-model="password" />
    </div>

    <div class="profession">
      <label for="profession">Role:</label>
      <br />
      <select id="profession" value="" v-model="role">
        <option value="developer">Web Developer</option>
        <option value="designer">Web Designer</option>
      </select>
    </div>

    <div class="skills">
      <label for="skill">Top 3 Skills: (seperate by ",")</label>
      <br />
      <input type="text" id="skill" v-model="tempSkill" @keyup="addSkill" />
      <span v-for="skill in skills" :key="skill.key">
        {{ skill.skillName }}
      </span>
    </div>
    <br />
    <div class="agree">
      <input class="check" id="check" type="checkbox" v-model="check" />
      <label for="check">I agree with all your requirments</label>
    </div>

    <br />
    <button :class="{disabled:!check}" :disabled="!check">Create an account</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      password: "",
      role: "",
      check: true,
      skills: [],
      tempSkill: "",
    };
  },
  methods: {
    addSkill(event) {
      if (this.skills.length < 3) {
        if (event.key === "," && this.tempSkill !== "") {
          this.skills.push({
            key: this.skills.length + 1,
            skillName: this.tempSkill.slice(0, this.tempSkill.length - 1),
          });
          this.tempSkill = "";
        }
      }
      else{
        alert("Please enter your top THREE skills!");
        this.tempSkill=""
      }
    },
    handleSubmit() {
      console.log(this.email);
      console.log(this.password);
      console.log(this.role);
      console.log(this.skills.target);
      this.init();
    },
    init() {
      this.email = "";
      this.password = "";
      this.role = "";
      this.skills = [];
    },
  },
};
</script>

<style scoped>
.form {
  width: 500px;
  height: 600px;
  padding: 50px 100px;
  justify-content: center;
  margin: auto;
  border-radius: 20px;
  background-color: white;
  font-size: 1.4em;
  border: solid rgb(160, 159, 159);
}
input {
  width: 500px;
  height: 40px;
  font-size: 0.8em;
  margin-bottom: 30px;
}
select {
  width: 500px;
  height: 40px;
  font-size: 0.7em;
  margin-bottom: 30px;
}

.check {
  width: 20px;
  height: 20px;
  font-size: 0.25em;
}
.agree {
  display: inline-block;
  width: 380px;
  height: 40px;
  font-size: 0.8em;
}

button {
  display: block;
  width: 190px;
  height: 60px;
  margin: 40px auto;
  border-radius: 10px;
  border: none;
  background-color: rgb(85, 158, 241);
  font-size: 0.8em;
  font-family: Arial, Helvetica, sans-serif;
  color: white;
  cursor: pointer;
}
.skills {
  max-width: 520px;
}

span {
  border: none;
  background-color: rgb(231, 231, 231);
  border-radius: 10px;
  margin: 10px 5px;
  padding: 10px;
}

.disabled{
    background-color: rgb(176, 213, 255);
}
</style>