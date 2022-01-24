<template>
  <div>
    <ul id="example-1">
      <li v-for="item in student" :key="item.ID">
        {{ item.GENDER }}
      </li>
    </ul>
  </div>
</template>

<script>
import { getstudent } from '@/api/yzg'
export default {
  data() {
    return {
      student: []
    }
  },
  created() {
    this.getstudent()
  },
  methods: {
    async getstudent() {
      const res = await getstudent()
      this.student = res.data
    }
  }
}
</script>

