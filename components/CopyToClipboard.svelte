<script>
  export let element = undefined;

  function copy() {
    if (element) {
      element.select();
      element.setSelectionRange(0, 99999);
      document.execCommand("copy");
    }
  }
</script>

<slot {copy} />
