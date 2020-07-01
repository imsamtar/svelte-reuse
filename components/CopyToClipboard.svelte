<script>
  import { createEventDispatcher } from "svelte";

  export let element = undefined;

  const dispatch = createEventDispatcher();

  function copy() {
    if (element) {
      element.select();
      element.setSelectionRange(0, 99999);
      document.execCommand("copy");
      dispatch("copy", null);
    } else {
      dispatch("fial", null);
    }
  }
</script>

<slot {copy} />
