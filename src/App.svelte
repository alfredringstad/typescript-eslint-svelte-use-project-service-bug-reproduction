<script lang="ts">
  let test = 56

  $: {
    const diff = 5;
    test += diff;
  }
</script>

{test}
