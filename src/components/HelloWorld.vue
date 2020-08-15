<template>
  <div>
    <nav>
      <label class="logo">DesignX</label>
      <input
        type="checkbox"
        id="check"
        class="check-1"
        :class="{check: checkbox}"
        v-model="checkbox"
      />
      <label for="check" class="checkbtn">
        <i class="fas fa-bars"></i>
      </label>

      <ul>
        <li>
          <a :class="{active: menu_1}" class="cursor" @click="come_pass()">Home</a>
        </li>
        <li>
          <a :class="{active: menu_2}" class="cursor" @click="go_pass()">About</a>
        </li>
        <li>
          <a :class="{active: menu_3}" class="cursor" href="#">Services</a>
        </li>
        <li>
          <a :class="{active: menu_4}" class="cursor" href="#">Contact</a>
        </li>
        <li>
          <a :class="{active: menu_5}" class="cursor" href="#">Feedback</a>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      checkbox: false,
      menu_1: false,
      menu_2: false,
      menu_3: false,
      menu_4: false,
      menu_5: false,
    };
  },
  methods: {
    come_pass() {
      this.$router.push("/");
      this.checkbox = false;
      this.menu_1 = true;
      this.menu_2 = false;
      this.menu_3 = false;
      this.menu_4 = false;
      this.menu_5 = false;
    },
    go_pass() {
      this.$router.push("/about");
      this.checkbox = false;
      this.menu_1 = false;
      this.menu_2 = true;
      this.menu_3 = false;
      this.menu_4 = false;
      this.menu_5 = false;
    },
  },
};
</script>

<style>
* {
  padding: 0;
  margin: 0;
  text-decoration: none;
  list-style: none;
  box-sizing: border-box;
}
.cursor {
  cursor: pointer;
}
body {
  font-family: montserrat;
}
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: #0082e6;
  height: 80px;
  width: 100%;
}
label.logo {
  color: white;
  font-size: 35px;
  line-height: 80px;
  padding: 0 100px;
  font-weight: bold;
}
nav ul {
  float: right;
  margin-right: 20px;
}
nav ul li {
  display: inline-block;
  line-height: 80px;
  margin: 0 5px;
}
nav ul li a {
  color: white;
  font-size: 17px;
  padding: 30px 13px;
  border-radius: 3px;
  text-transform: uppercase;
}
a.active,
a:hover {
  background: #1b9bff;
  padding: 30px 13px 40px 13px;
  transition: 0.5s;
}
.checkbtn {
  font-size: 30px;
  color: white;
  float: right;
  line-height: 80px;
  margin-right: 40px;
  cursor: pointer;
  display: none;
}
.check-1 {
  display: none;
}
@media (max-width: 952px) {
  label.logo {
    font-size: 30px;
    padding-left: 50px;
  }
  nav ul li a {
    font-size: 16px;
  }
}
@media (max-width: 858px) {
  .checkbtn {
    display: block;
  }
  ul {
    position: fixed;
    width: 100%;
    height: 100vh;
    background: #2c3e50;
    top: 80px;
    left: -100%;
    text-align: center;
    transition: all 0.5s;
  }
  nav ul li {
    display: block;
    margin: 50px 0;
    line-height: 30px;
  }
  nav ul li a {
    font-size: 20px;
  }
  a:hover,
  a.active {
    background: none;
    color: #0082e6;
  }
  .check:checked ~ ul {
    left: 0;
  }
}
</style>
