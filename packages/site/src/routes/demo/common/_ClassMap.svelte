<div>
  <Button
    class={classMap({
      'my-button': true,
      big: big,
      [color]: true,
    })}
  >
    <Label>I'm a Colored Button</Label>
  </Button>
</div>

<div>
  <FormField style="margin-right: 1em;">
    <Checkbox bind:checked={big} />
    {#snippet label()}
      Big
    {/snippet}
  </FormField>
  {#each ['red', 'blue', 'green'] as option}
    <FormField style="margin-right: 1em;">
      <Radio bind:group={color} value={option} />
      {#snippet label()}
        {`${option[0].toUpperCase()}${option.slice(1)}`}
      {/snippet}
    </FormField>
  {/each}
</div>

<script lang="ts">
  import { classMap } from '@smui/common/internal';
  import { Label } from '@smui/common';
  import Button from '@smui/button';
  import FormField from '@smui/form-field';
  import Radio from '@smui/radio';
  import Checkbox from '@smui/checkbox';

  let big = $state(false);
  let color = $state('red');
</script>

<style>
  * :global(.my-button) {
    margin: 0.5em;
  }

  * :global(.red) {
    color: red;
  }
  * :global(.blue) {
    color: blue;
  }
  * :global(.green) {
    color: green;
  }

  * :global(.big) {
    font-size: 1.5em;
  }
</style>
