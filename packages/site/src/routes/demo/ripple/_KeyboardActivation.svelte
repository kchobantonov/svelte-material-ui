<div
  use:Ripple={{ surface: true, active }}
  onmousedowncapture={() => (active = true)}
  onmouseupcapture={() => (active = false)}
  onkeydowncapture={(e) => (active = e.code === 'Space' || e.code === 'Enter')}
  onkeyupcapture={() => (active = false)}
  tabindex="0"
  role="button"
>
  Keyboard activation on an arbitrary element. (Focus and press space/enter.)
</div>

<script lang="ts">
  import Ripple from '@smui/ripple';

  let active = $state(false);
</script>

<style>
  div {
    padding: 10px;
    border-radius: 5px;
  }

  [tabindex='0'] {
    cursor: pointer;
  }
</style>
