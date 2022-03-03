<template>
  <div>
    <div align="left">
      <v-btn
        light
        fab
        color="#94B3FD"
        href="/firstpage"
      >
        <v-icon x-large color="#000">
          mdi-door-open
        </v-icon>
      </v-btn>
    </div>
    <br><br>
    <v-card class="ma-2 card1 drop" light elevation="3">
      <div class="text-center drop">
        <v-icon style="font-size: 120px;">
          mdi-account-circle
        </v-icon>
      </div>
      <br>
      <li v-for="us in register" :key="us.r_id">
        <v-text-field v-model="us.user" outlined rounded>
          ชื่อ : {{ us.user }}
        </v-text-field>
        <v-text-field v-model="us.email " outlined rounded>
          อีเมลล์ : {{ us.email }}
        </v-text-field>
        <v-text-field v-model="us.passwd" outlined rounded type="password">
          รหัสผ่าน : {{ us.passwd }}
        </v-text-field>
      </li>
      <br><br><br><br>
      <div class="text-center">
        <v-btn
          color="#C294FF"
          rounded
          class="btn1"
          dark
          href="/firstpage"
        >
          <v-icon>mdi-pencil</v-icon> บันทึก
        </v-btn>

        <v-btn
          color="#C294FF"
          rounded
          dark
          class="btn1"
          href="/login"
        >
          <v-icon>mdi-logout</v-icon> ล็อกเอาท์
        </v-btn>
      </div>
      <br>
    </v-card>
  </div>
</template>
<script>

export default {
  data: () => ({
    user: '',
    passwd: '',
    dialog: false,
    dialog_false: false,
    fullname: '',
    register: [
      { r_id: '005', user: 'Name5', email: 'Name1', passwd: '123456' }
    ]
  }),
  created () {
    this.showData()
  },
  methods: {
    async showData () {
      console.log('Showdata')
      // http://localhost:7005/save?name=%27alonkorn%27&age=48
      const res = await fetch('http://localhost:7001/list10')
      // const data = res.json()
      const data = await res.json()
      this.register = data.value
      console.log(this.register)
    }
  }
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Kanit:ital,wght@0,100;0,300;1,100;1,200;1,300&display=swap');
h2{
  color: #000;
  margin-top: 30px;
  font-family: 'Kanit',sans-serif;
  margin-bottom: 30px;
}
.card1{
  padding: 14px;
}
.btn1{
  width: 140px;
  margin: 10px;
  font-family: 'kanit',sans-serif;
}

</style>
