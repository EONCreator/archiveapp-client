<style>
    body {

  display: flex;
  justify-content: center;
  min-height: 100vh;
    }

    .form {
        margin-top: 40px;
        width: 370px;
        height: 550px;
        color: rgb(56, 56, 56);
        background: white;
    }

    .form .content {
        padding: 35px;
        padding-bottom: 15px;
        display: block;
    }

    .form .control {
        width: 100%;
        padding: 10px 0;
    }

    input {
        padding: 12px;
        font-size: 15px;
        width: 100%;
        outline: none;
        border: none;
        border: 1px solid lightgray;
        border-radius: 5px;
    }

    button {
        width: 100%;
        padding: 12px;
        outline: none;
        cursor: pointer;
        border: none;
        background-color: rgb(69, 112, 255);
        color: white;
    }

    button:hover {
        background-color: rgb(39, 89, 255);
    }

    label {
        font-size: 13px;
        color: rgb(78, 78, 78);
    }

    .header {
        font-size: 22px;
        font-weight: 370;
        padding: 10px;
        padding-top: 35px;
        display: flex;
        justify-content: center;
    }

    .footer {
        padding: 25px 20px;
        padding-top: 0;
        display: flex;
        justify-content: center;
        text-align: center;
    }

    .error {
        color: rgb(255, 14, 14);
    }

    .success {
        color: #009607;
    }
</style>

<template>
    <div class="form">
        <div class="header"><img width="128" src="./../../../public/logo.jpg"></div>
        <div class="content">
            <div class="control">
                <input v-model="email" placeholder="Введите email"/>
            </div>
            <div class="control">
                <input v-model="userName" placeholder="Введите имя пользователя"/>
            </div>
            <div class="control">
                <input v-model="password" placeholder="Введите пароль" type="password" />
            </div>
            <div class="control">
                <button @click="signup">OK</button>
            </div>
        </div>
        <div class="footer">
            <div :class="[success ? 'success' : 'error']">
                {{ success ? "Регистрация прошла успешно" : error }}
            </div>
        </div>
    </div>
</template>

<script>
    import axios from 'axios'

export default {
  data() {
    return {
      success: false,
      userName: null,
      password: null,
      email: null,
      error: null
    }
  },
  methods: {
    async signup() {
        var userName = this.userName
        var password = this.password
        var email = this.email
        await axios.post("http://217.171.146.249/api/user/signup", { userName, password, email })
        .then(e => {
            this.success = true
        })
        .catch(err => {
            this.success = false
            this.error = "Пользователь с таким email уже существует"
        })
    }
  }
}
</script>