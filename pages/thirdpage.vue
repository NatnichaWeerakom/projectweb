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
    <v-responsive
      class="overflow-y-auto"
      max-height="550"
    >
      <div>
        <h2>สัปดาห์ที่ 1</h2>
      </div>
      <div class="drop" align="right">
        <v-textarea
          rounded
          outlined
          dense
          label="โปรดกรอกรายละเอียดกิจกรรม"
        />
        <br>

        <v-simple-table light>
          <thead>
            <tr>
              <th class="text-left">
                ชื่อ
              </th>
              <th class="text-left">
                นามสกุล
              </th>
              <th class="text-left">
                การเข้าร่วม
              </th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="item in student" :key="item.student_id">
              <td>{{ item.std_name }}</td>
              <td>{{ item.std_lastname }}</td>
              <td>
                <v-radio-group
                  v-model="row"
                >
                  <v-radio
                    label="เข้าร่วม"
                    value="เข้าร่วม"
                  />
                  <v-radio
                    label="ไม่เข้าร่วม"
                    value="ไม่เข้าร่วม"
                  />
                </v-radio-group>
              </td>
            </tr>
          </tbody>
        </v-simple-table>
        <v-btn
          href="/firstpage"
          color="blue darken-3"
          rounded
          class="btn1 drop3"
          dark
          elevation="0"
        >
          SAVE
        </v-btn>
      </div>
    </v-responsive>
  </div>
</template>
<script>
export default {
  data: () => ({
    drawer: false,
    group: null,
    selectedItem: 1,
    student: [
      { student_id: '001', std_name: 'นายปฎิมากร', std_lastname: 'เจนจิต' },
      { student_id: '002', std_name: 'นายอภิรักษ์', std_lastname: 'กาเวสูง' },
      { student_id: '003', std_name: 'นายธนโชติ', std_lastname: 'จ่าแก้ว' },
      { student_id: '004', std_name: 'นายปิยศักดิ์', std_lastname: 'จันทร์ต้น' },
      { student_id: '005', std_name: 'นายภูรินทร์', std_lastname: 'โม้อุ่น' },
      { student_id: '006', std_name: 'นายณัฐดนัย', std_lastname: 'จันภักดี' },
      { student_id: '007', std_name: 'นายภัทรพงษ์', std_lastname: 'อาจโยธี' },
      { student_id: '008', std_name: 'นายกฤษฎา', std_lastname: 'มาตรโคกสูง' },
      { student_id: '009', std_name: 'นายวันชัย', std_lastname: 'วัฒนะ' },
      { student_id: '010', std_name: 'นายวีรภัทร', std_lastname: 'ฉัตรหลวง' }
    ]
  }),
  created () {
    this.showData()
  },
  methods: {
    async showData () {
      console.log('Showdata')
      // http://localhost:7005/save?name=%27alonkorn%27&age=48
      const res = await fetch('http://localhost:7001/list_std')
      // const data = res.json()
      const data = await res.json()
      this.student = data.value
      console.log(this.student)
    },
    watch: {
      group () {
        this.drawer = false
      }
    }
  }
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Kanit:ital,wght@0,100;0,300;1,100;1,200;1,300&display=swap');

.bg{
  font-family: 'Kanit',sans-serif;
}
h2{
  color: black;
  font-family: 'Kanit',sans-serif;
  margin-top: 2rem;

}
.drop{
  margin-top: 30px;
  border-radius: 20px ;
}
.drop3{
  margin-bottom: 30px;
  margin-top: 30px;
}
.v-textarea{
  background-color: #94DAFF;
}
.v-simple-table{
  margin-bottom: 30px;
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
