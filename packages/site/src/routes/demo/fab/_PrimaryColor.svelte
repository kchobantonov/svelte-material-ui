<div class="flexy">
  <div class="margins">
    <Fab color="primary" onclick={() => clicked++}>
      <Icon class="material-icons">favorite</Icon>
    </Fab>
  </div>
</div>

<pre class="status">Clicked: {clicked}</pre>

<script lang="ts">
  import Fab, { Icon } from '@smui/fab';

  let clicked = $state(0);
</script>
