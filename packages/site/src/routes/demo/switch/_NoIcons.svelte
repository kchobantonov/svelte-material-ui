<div>
  <FormField>
    <Switch bind:checked={checked1} icons={false} />
    {#snippet label()}
      Fields of grain.
    {/snippet}
  </FormField>
</div>

<pre class="status">Checked: {checked1}</pre>

<div style="margin-top: 1em;">
  <FormField>
    <Switch bind:checked={checked2} color="secondary" icons={false} />
    {#snippet label()}
      Fields of grain.
    {/snippet}
  </FormField>
</div>

<pre class="status">Checked: {checked2}</pre>

<script lang="ts">
  import Switch from '@smui/switch';
  import FormField from '@smui/form-field';

  let checked1 = $state(false);
  let checked2 = $state(false);
</script>
