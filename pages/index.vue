<template>
  <v-row justify="center" align="center">
    <div class="bg" />
    <v-col cols="12" sm="8" md="6">
      <div class="logo">
        <v-img src="/class.png" />
      </div>
      <v-btn class="btn1" x-large color="#94B3FD" href="login">
        <span class="txt1" ><i class="fas fa-sign-in-alt" /> เริ่ม</span>
      </v-btn>
    </v-col>
  </v-row>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Itim&family=Kanit:ital,wght@0,100;0,300;1,100;1,200;1,300&display=swap');
.bg{
  background-image: url("/bg3.jpg");
  background-size: cover;
}
.logo{
  margin-top: 130px;
}
.btn1{
  border-radius: 30px;
  margin-top: 70px;
  margin-left: 15px;
  font-family: 'Kanit',sans-serif;
}
.txt1{
  font-size: 24px;
}
.img1{
  margin-bottom: 45px;
}
</style>
