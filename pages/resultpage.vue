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
                mdi-account
              </v-icon>
            </v-btn>
          </div>
        </v-col-sm-6>
      </v-row>
    </v-container-fluid>

    <h2>ผลการตัดกิจกรรม</h2>
    <div class="rounded-xl white text-center">
      <div class="txt01">
        <p>รายชื่อผู้ไม่ผ่านกิจกรรม</p>
      </div>
      <v-simple-table light>
        <template #default>
          <thead>
            <tr>
              <th class="text-left">
                No
              </th>
              <th class="text-left">
                ID
              </th>
              <th class="text-left">
                Name
              </th>
              <th class="text-left">
                Surname
              </th>
            </tr>
          </thead>
          <tbody>
            <tr
              v-for="st in student"
              :key="st.id"
            >
              <td>{{ st.number }}</td>
              <td>{{ st.r_id }}</td>
              <td>{{ st.fullname }}</td>
              <td>{{ st.email }}</td>
            </tr>
          </tbody>
        </template>
      </v-simple-table>
      <p>_________________________________</p>
      <p>หมายเหตุ <br> เกณฑ์การตัดกิจกรรมคือ 60%</p>
    </div>
  </div>
</template>
<script>
export default {
  layout: 'la_student',
  data () {
    return {
      username: '',
      bacount: '',
      mobile: '',
      email: '',
      passwd: '',
      student: [
        { number: '1', r_id: '63309010001', fullname: 'Natnicha', email: 'test1' },
        { number: '1', r_id: '63309010002', fullname: 'Jeerawan', email: 'test2' },
        { number: '1', r_id: '63309010003', fullname: 'Narirat', email: 'test3' },
        { number: '1', r_id: '63309010004', fullname: 'Teerapong', email: 'test4' },
        { number: '1', r_id: '63309010005', fullname: 'Supaporn', email: 'test5' }
      ]
    }
  },
  computed: {
    upperName () {
      return this.name.toUpperCase()
    }
  },
  created () {
    this.Show()
  },
  methods: {
    async Show () {
      console.log('show data')
      const res = await fetch('http://localhost:7001/list')
      const data = await res.json()
      this.student = data.datas
      console.log(data.datas)
    },
    edit (rid) {
      console.log('rid = ', rid)
      this.$router.push('edit_std?rid=' + rid)
    },
    del () {

    }
  }
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Kanit:ital,wght@0,100;0,300;1,100;1,200;1,300&display=swap');

h2{
  font-family: 'kanit',sans-serif;
  color: #000;
  margin: 20px;
}

.txt01{
  margin: 20px;
  color: #000;
}
p{
  color: #000;
}
td{
  text-align: left;
}
.edit{
 margin: 5px;
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
