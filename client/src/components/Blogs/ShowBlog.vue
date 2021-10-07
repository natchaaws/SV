<template>
  <div>

   <b-container class="bv-example-row">
      <b-row class="text-left">
        <b-col></b-col>

        <b-col cols="10" class="bg1">

    <h1>ตรวจสอบการจอง {{ blog.id }} </h1><hr>


    <p>ลำดับ: {{ blog.id }}</p>
      <p>ชื่อ: {{ blog.firstname }}</p>
      <p>นามสกุล: {{ blog.lastname }}</p>
      <p>ชื่อห้องประชุม: {{ blog.nroom }}</p>
      <p>จำนวนผู้เข้าประชุม: {{ blog.pnum }}</p>
      <p>เบอร์โทรศัพท์: {{ blog.tel }}</p>
      <p>วันที่เริ่มต้น: {{ blog.dates }}</p>
      <p>เวลาที่เริ่มต้น: {{ blog.times }}</p>
      <p>วันที่สิ้นสุด: {{ blog.datee }}</p>
      <p>เวลาที่สิ้นสุด: {{ blog.timee }}</p>
      <p>อื่นๆ : {{ blog.other }}</p>

    <p>
      <b-button pill variant="warning" v-on:click="navigateTo('/blog/edit/' + blog.id)">
        แก้ไขการจอง
      </b-button>
      <b-button pill variant="secondary" v-on:click="navigateTo('/blogs')">ย้อนกลับ</b-button>
    </p>

    </b-col>
      <b-col> </b-col>
     </b-row>
</b-container>

  </div>
</template>

<script>
import BlogService from "@/services/BlogsService";
export default {
  data() {
    return {
      blog: null,
    };
  },
  async created() {
    try {
      let blogId = this.$route.params.blogId;
      this.blog = (await BlogService.show(blogId)).data;
    } catch (error) {
      console.log(error);
    }
  },
  methods: {
    navigateTo(route) {
      this.$router.push(route);
    },
  },
};
</script>
<style scoped>
</style>