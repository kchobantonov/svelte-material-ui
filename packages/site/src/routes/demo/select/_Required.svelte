<div class="columns margins">
  <div>
    <Select bind:value={valueA} label="Standard" required>
      <Option value="" />
      {#each fruits as fruit}
        <Option value={fruit}>{fruit}</Option>
      {/each}
    </Select>

    <pre class="status">Selected: {valueA}</pre>
  </div>

  <div>
    <Select variant="filled" bind:value={valueB} label="Filled" required>
      <Option value="" />
      {#each fruits as fruit}
        <Option value={fruit}>{fruit}</Option>
      {/each}
    </Select>

    <pre class="status">Selected: {valueB}</pre>
  </div>

  <div>
    <Select variant="outlined" bind:value={valueC} label="Outlined" required>
      <Option value="" />
      {#each fruits as fruit}
        <Option value={fruit}>{fruit}</Option>
      {/each}
    </Select>

    <pre class="status">Selected: {valueC}</pre>
  </div>
</div>

<script lang="ts">
  import Select, { Option } from '@smui/select';

  let fruits = ['Apple', 'Orange', 'Banana', 'Mango'];

  let valueA = $state('');
  let valueB = $state('');
  let valueC = $state('');
</script>
