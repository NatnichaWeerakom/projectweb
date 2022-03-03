<template>
  <div>
    <v-card light color="#C294FF">
      <h2 >EDIT STUDENT</h2>
      <form>
        <v-text-field outlined rounded v-model="student_id" label="รหัสนักศึกษา" />
        <v-text-field outlined rounded v-model="std_name" label="ชื่อ" />
        <v-text-field outlined rounded v-model="std_lastname" label="สกุล" />
        <v-btn class="mr-4" color="#94B3FD" href="stdpage">
          submit
        </v-btn>
        <v-btn @click="onClear" color="#94B3FD">
          clear
        </v-btn>
      </form>
    </v-card>
  </div>
</template>
<script>
// import axios from 'axios'
export default {
  data () {
    return {
      student_id: '',
      std_name: '',
      std_lastname: ''
    }
  }
  // async created () {
  //   console.log('student_id=', this.$route.body.student_id)
  //   this.student_id = this.$route.body.student_id
  //   const res = await axios.post(
  //     'http://localhost:7001/edit?student_id=' + this.student_id
  //   )
  //   // eslint-disable-next-line no-unused-vars
  //   const data = await res.json()
  //   this.student_id = data.value.student_id
  //   this.std_name = data.value.std_name
  //   this.std_lastname = data.value.std_lastname
  //   // this.code = this.$route.body.code
  //   console.log('data', data.value)
  // },
  // methods: {
  //   async onSave () {
  //     const student = {
  //       student_id: this.student_id,
  //       std_name: this.std_name,
  //       std_lastname: this.std_lastname

  //     }
  //     // console.log("std=", student)
  //     const res = await axios.post('http://localhost:7001/save1', student)
  //     console.log(res.data)
  //     if (res.data.status === 1) {
  //       this.$router.push('/stdpage')
  //     }
  //   },
  //   onClear () {}
  // }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Kanit:ital,wght@0,100;0,300;1,100;1,200;1,300&display=swap');

h2{
  font-family: 'kanit',sans-serif;
  margin: 40px;
  color: #000;
}
.v-text-field{
 font-family: 'kanit',sans-serif;
}
</style>
