<!--
  Note: chips must be unique. (They cannot === each other.)
  If you need to show the same value, use keyed chips.
-->
<Set chips={['one', 'two', 'three', 'four', 'five']}>
  {#snippet chip(chip)}
    <!-- Note: the `chip` property is required! -->
    <Chip
      {chip}
      shouldRemoveOnTrailingIconClick={false}
      onclick={() => clicked++}
    >
      {#if chip === 'four'}
        <LeadingIcon class="material-icons">book</LeadingIcon>
      {/if}
      <Text tabindex={0}>{chip}</Text>
      {#if chip === 'five'}
        <TrailingIcon class="material-icons">commute</TrailingIcon>
      {/if}
    </Chip>
  {/snippet}
</Set>

<pre class="status">Clicked: {clicked}</pre>

<script lang="ts">
  import Chip, { Set, LeadingIcon, TrailingIcon, Text } from '@smui/chips';

  let clicked = $state(0);
</script>
