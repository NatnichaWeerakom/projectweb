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
          <div class="my-6">
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

    <div class="txt01">
      <h2>รายชื่อนักเรียน / นักศึกษา</h2>
      <div class="rounded-xl text-center">
        <v-responsive
          class="overflow-y-auto"
          max-height="500"
        >
          <v-simple-table dense light>
            <template #default>
              <thead>
                <tr>
                  <th class="text-left">
                    ID
                  </th>
                  <th class="text-left">
                    Name
                  </th>
                  <th class="text-left">
                    lastname
                  </th>
                  <th class="text-left">
                    Edit /Delete
                  </th>
                </tr>
              </thead>
              <tbody>
                <tr
                  v-for="st in student"
                  :key="st.student_id"
                >
                  <td>{{ st.student_id }}</td>
                  <td>{{ st.std_name }}</td>
                  <td>{{ st.std_lastname }}</td>
                  <v-btn
                    class="edit"
                    color="warning"
                    rounded
                    href="edit_std"
                  >
                    edit
                  </v-btn>
                  <v-btn
                    class="del"
                    color="red"
                    rounded
                    dark
                    @click="del(st.student_id)"
                  >
                    del
                  </v-btn>
                </tr>
              </tbody>
            </template>
          </v-simple-table>
        </v-responsive>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  layout: 'la_student',
  data () {
    return {
      student: [
        { student_id: '63309010001', std_name: 'Natnicha', std_lastname: 'test1' },
        { student_id: '63309010002', std_name: 'Jeerawan', std_lastname: 'test2' },
        { student_id: '63309010003', std_name: 'Narirat', std_lastname: 'test3' },
        { student_id: '63309010004', std_name: 'Teerapong', std_lastname: 'test4' },
        { student_id: '63309010005', std_name: 'Supaporn', std_lastname: 'test5' }
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
      const res = await fetch('http://localhost:7001/list_class')
      const data = await res.json()
      this.student = data.row
      console.log(data.row)
    }
    // edit (studentid) {
    //   console.log('student_id=', studentid)
    //   this.$router.push('edit_std?student_id=' + studentid)
    // },
    // async del (studentid) {
    //   console.log('student_id=', studentid)
    //   const res = await fetch(
    //     'http://localhost:7001/del?student_id=' + studentid
    //   )
    //   // const data = res.json()
    //   const data = await res.json()
    //   console.log('data=', data)
    // }
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
