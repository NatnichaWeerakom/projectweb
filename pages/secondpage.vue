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
    <h2>บันทึกกิจกรรม</h2>

    <!--menus-->
    <v-responsive
      class="overflow-y-auto"
      max-height="550"
    >
      <div
        v-for="item in items "
        :key="item.text"
        class="my-2"
      >
        <v-btn
          x-large
          color="#94B3FD"
          style="width:250px;   height: 90px;"
          rounded
          href="thirdpage"
        >
          {{ item.text }}
        </v-btn>
      </div>
</v-responsive>
  </div>
</template>
<script>
export default {
  data: () => ({
    selectedItem: 1,
    items: [
      { text: 'สัปดาห์ที่ 1' },
      { text: 'สัปดาห์ที่ 2' },
      { text: 'สัปดาห์ที่ 3' },
      { text: 'สัปดาห์ที่ 4' },
      { text: 'สัปดาห์ที่ 5' },
      { text: 'สัปดาห์ที่ 6' },
      { text: 'สัปดาห์ที่ 7' },
      { text: 'สัปดาห์ที่ 8' }
    ]
  })
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Itim&family=Kanit:ital,wght@0,100;0,300;1,100;1,200;1,300&display=swap');

h2{
  color: black;
  font-family: 'Kanit',sans-serif;
  margin-top: 2.6rem;

}
.btnlogout{
  margin: 60px;
  padding-left: 145px;
}
.mx-auto{
  margin-top: 50px;
}
.v-list-item{
  padding-top: 60px;
}
</style>
