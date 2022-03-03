<template>
  <div>
    <v-container-fluid>
      <v-row justify="space-around">
        <v-col-sm-6>
          <!--backbtn-->
          <div class="my-5">
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
        </v-col-sm-6>
        <!--profilebtn-->
        <v-col-sm-6>
          <div class="my-6" >
            <v-btn
              light
              fab
              color="#94B3FD"
              href="/profile"
            >
              <v-icon x-large color="#000">
                mdi-account-circle
              </v-icon>
            </v-btn>
          </div>
        </v-col-sm-6>
      </v-row>
    </v-container-fluid>

    <h2>ภาพรวมกิจกรรม</h2>
    <v-progress-circular
      :value="80"
      :size="200"
      :width="50"
      color="deep-purple lighten-2"
    />
    <p>ผู้เข้าร่วมกิจกรรม <br> คิดเป็น 80 %</p>
    <p>ผู้ไม่เข้าร่วมกิจกรรม <br> คิดเป็น 20 %</p>
  </div>
</template>
<script>

</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Kanit:ital,wght@0,100;0,300;1,100;1,200;1,300&display=swap');
h2{
  color: #000;
  margin-top: 30px;
  font-family: 'Kanit',sans-serif;
  margin-bottom: 30px;
}
p{
  font-size: 20px;
  font-family: 'Kanit',sans-serif;
  color: #000;
  margin-top: 40px;
  margin-bottom: 40px;
}
.my-6{
  padding-bottom: 120px;
  padding: 0%;
  margin-left: 70px;
}
.my-5{
  padding-bottom: 120px;
  padding: 0%;
  margin-right: 90px;
}
</style>
