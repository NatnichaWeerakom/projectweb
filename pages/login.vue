<template>
  <v-card
    light
    class="box"
  >
    <div class="bg1">
      <div class="text-center">
        <v-dialog
          v-model="dialog"
          width="500"
        >
          <v-card>
            <v-card-title class="text-h5 blue lighten-2">
              Status Login
            </v-card-title>

            <v-card-text>
              SUCCESS LOGIN
            </v-card-text>

            <v-divider />
          </v-card>
        </v-dialog>

        <v-dialog
          v-model="dialog_false"
          width="500"
        >
          <v-card>
            <v-card-title class="text-h5 red lighten-2">
              Status Login
            </v-card-title>

            <v-card-text>
              Error LOGIN
            </v-card-text>

            <v-divider />
          </v-card>
        </v-dialog>

        <v-row justify="center" align="center">
          <v-col>
            <h1>กิจกรรมชมรม</h1>

            <v-form>
              <v-text-field
                v-model="user"
                label="Username or Email"
                outlined
                style="padding: 50px 20px 0px 20px;  "
                prepend-inner-icon="mdi-account"
              />
              <v-text-field
                v-model="passwd"
                label="Password"
                type="password"
                outlined
                style="padding: 0px 20px 0px 20px;"
                prepend-inner-icon="mdi-lock"
                append-icon="mdi-eye-off"
              />
              <v-btn class="btn1" rounded @click="onSave">
                <span class="txt1">ล็อกอิน</span>
              </v-btn>
            </v-form>
          </v-col>
        </v-row>
      </div>
    </div>
  </v-card>
</template>

<script>
import axios from 'axios'
export default {
  data: () => ({
    user: '',
    passwd: '',
    dialog: false,
    dialog_false: false
  }),
  methods: {
    async onSave () {
      const std = {
        user: this.user,
        passwd: this.passwd
      }
      console.log('username:', std)
      const res = await axios.post('http://localhost:7001/list_user', std)
      console.log(res.data)
      try {
        if (res.data.status > 0) {
          console.log('Login successful')
          this.dialog = true
          this.user = ''
          this.passwd = ''
          setInterval(() => {
            this.dialog = false
            this.$router.push('/firstpage')
          }, 2000)
        } else {
          this.dialog_false = true
          setInterval(() => {
            this.dialog_false = false
            this.$router.push('/login')
          }, 3000)
        }
      } catch (error) {
        console.log('Error Login')
      }
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Itim&family=Kanit:ital,wght@0,100;0,300;1,100;1,200;1,300&display=swap');

.box{
  font-family: 'Kanit',sans-serif;
}
.bg1{
  background-image: url("/bg2.jpg");
  background-size: cover;
  background-color:#acf8f9;
}
h1{
  margin-top: 200px;
  color: #B983FF;
  font-family: 'Kanit',sans-serif;
  text-shadow: #7fbdcf 0.1em 0.1em 0.2em;
}
.v-text-field--outlined fieldset{
  border-radius: 30px;
  background: #61bbeb;

}
.btn1{
  background: linear-gradient(to bottom,#94daff,#61bbeb);
  margin-top: 7px;
  margin-bottom: 12rem;
}
.txt1{
  color: rgb(255, 255, 255);
  font-size: 24px;
  font-family: 'Kanit',sans-serif;
}
</style>
