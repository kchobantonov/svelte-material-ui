<div style="display: flex; align-items: center;">
  <IconButton onclick={() => toggleClicked++} toggle bind:pressed={initialOff}>
    <Icon class="material-icons" on>star</Icon>
    <Icon class="material-icons">star_border</Icon>
  </IconButton>
</div>
<div style="display: flex; align-items: center;">
  <IconButton onclick={() => toggleClicked++} toggle bind:pressed={initialOn}>
    <Icon class="material-icons" on>alarm_on</Icon>
    <Icon class="material-icons">alarm_off</Icon>
  </IconButton>

  &nbsp;

  <!-- Note: this doesn't fire the MDCIconButtonToggle:change event. -->
  <Button onclick={() => (initialOn = !initialOn)}>
    <Label>Toggle Programmatically</Label>
  </Button>
</div>
<div style="display: flex; align-items: center;">
  <!-- Note: don't use `toggle` prop in this case. -->
  <IconButton
    onclick={() => {
      toggleClicked++;
      usingEvents = !usingEvents;
    }}
    pressed={usingEvents}
  >
    <Icon class="material-icons" on>bookmark</Icon>
    <Icon class="material-icons">bookmark_border</Icon>
  </IconButton>&nbsp;Using events instead of bound variables.
</div>

<pre class="status">Clicked: {toggleClicked}</pre>

<script lang="ts">
  import IconButton, { Icon } from '@smui/icon-button';
  import Button, { Label } from '@smui/button';

  let toggleClicked = $state(0);
  let initialOff = $state(false);
  let initialOn = $state(true);
  let usingEvents = $state(false);
</script>
