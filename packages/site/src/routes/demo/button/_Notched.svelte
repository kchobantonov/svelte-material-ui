<Button onclick={() => clicked++} variant="raised" class="button-shaped-notch">
  <Label>Raised</Label>
</Button>
<Button
  onclick={() => clicked++}
  variant="unelevated"
  class="button-shaped-notch"
>
  <Label>Unelevated</Label>
</Button>
<Button
  onclick={() => clicked++}
  variant="unelevated"
  class="button-shaped-notch"
>
  <Icon class="material-icons">favorite</Icon>
  <Label>Icon</Label>
</Button>
<Button
  onclick={() => clicked++}
  variant="unelevated"
  class="button-shaped-notch"
>
  <Label>Trailing Icon</Label>
  <Icon class="material-icons">favorite</Icon>
</Button>

<pre class="status">Clicked: {clicked}</pre>

<script lang="ts">
  import Button, { Label, Icon } from '@smui/button';

  let clicked = $state(0);
</script>
