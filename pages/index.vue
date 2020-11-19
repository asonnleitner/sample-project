<template>
  <div>
    <WithImport/>
    <WithoutImport/>
  </div>
</template>

<script>
import WithImport from "~/pages/WithImport";
import WithoutImport from "~/pages/WithoutImport";

export default {
  name: 'index',
  components: {WithoutImport, WithImport}
}
</script>
