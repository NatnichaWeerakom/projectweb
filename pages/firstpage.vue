<template>
  <div>
    <div align="right">
      <v-btn
        light
        fab
        color="#94B3FD"
        href="/profile"
      >
        <v-icon x-large color="#000">
          mdi-account
        </v-icon>
      </v-btn>
    </div>
    <h2>หน้าแรก</h2>

    <!--menus-->
   <div class="my-2">
      <v-btn
        x-large
        color="#94B3FD"
        style="width:250px;   height: 90px;"
        rounded
        href="secondpage"
      > <v-icon>mdi-book</v-icon>
        บันทึกกิจกรรม
      </v-btn>
    </div>
    <div class="my-2">
      <v-btn
        x-large
        color="#94B3FD"
        style="width:250px;   height: 90px;"
        rounded
        href="grappage"
      > <v-icon>mdi-flag</v-icon>
        ภาพรวมกิจกรรม
      </v-btn>
    </div>
    <div class="my-2">
      <v-btn
        x-large
        color="#94B3FD"
        style="width:250px;   height: 90px;"
        rounded
        href="stdpage"
      > <v-icon>mdi-account</v-icon>
        รายชื่อนักเรียนนักศึกษา
      </v-btn>
    </div>
    <div class="my-2">
      <v-btn
        x-large
        color="#94B3FD"
        style="width:250px;   height: 90px;"
        rounded
        href="resultpage"
      > <v-icon>mdi-school</v-icon>
         ผลการตัดกิจกรรม
      </v-btn>
    </div>

    <!--btn logout-->
    <div class="btnlogout">
      <v-btn
        rounded
        color="error"
        dark
        href="login"
      >
        <v-icon
          right
          dark
        >
          mdi-logout
        </v-icon> &nbsp;
        ออกจากระบบ
      </v-btn>
    </div>
  </div>
</template>
<script>
export default {
  data: () => ({
    selectedItem: 1
  })
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Itim&family=Kanit:ital,wght@0,100;0,300;1,100;1,200;1,300&display=swap');

h2{
  color: black;
  font-family: 'Kanit',sans-serif;
  margin-top: 1rem;
}
.btnlogout{
  margin-top: 20px;
  margin-left: 80px;
}
.my-2{
  padding-top: 30px;
  font-family: 'Kanit',sans-serif;
}
</style>
