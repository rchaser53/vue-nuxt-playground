<template>
  <div @click="throwError">
    nya-n
  </div>
</template>

<script>
export default {
  mounted() {
    console.log('mounted child')
    // a
    throw new Error('test mounted error2')
  },
  methods: {
    throwError() {
      // a
      // throw new Error('hoge-')
    }
  },
  // errorCaptured(err, vm, info) {
  //   console.log(err, "kokonihakuru");
  //   return false;
  // }
}
</script>