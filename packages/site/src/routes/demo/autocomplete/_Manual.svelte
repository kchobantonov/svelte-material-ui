<div class="columns margins">
  <div>
    <Autocomplete
      options={fruits}
      bind:value={valueStandard}
      bind:text={textStandard}
    >
      <Textfield label="Fruit" bind:value={textStandard} />
    </Autocomplete>

    <pre class="status">Selected: {valueStandard || ''}</pre>
  </div>

  <div>
    <Autocomplete
      options={fruits}
      bind:value={valueFilled}
      bind:text={textFilled}
    >
      <Textfield label="Fruit" bind:value={textFilled} variant="filled" />
    </Autocomplete>

    <pre class="status">Selected: {valueFilled || ''}</pre>
  </div>

  <div>
    <Autocomplete
      options={fruits}
      bind:value={valueOutlined}
      bind:text={textOutlined}
    >
      <Textfield label="Fruit" bind:value={textOutlined} variant="outlined" />
    </Autocomplete>

    <pre class="status">Selected: {valueOutlined || ''}</pre>
  </div>
</div>

<script lang="ts">
  import Autocomplete from '@smui-extra/autocomplete';
  import Textfield from '@smui/textfield';

  let fruits = ['Apple', 'Orange', 'Banana', 'Mango'];

  let valueStandard: string | undefined = $state();
  let textStandard = $state('');
  let valueFilled: string | undefined = $state();
  let textFilled = $state('');
  let valueOutlined: string | undefined = $state();
  let textOutlined = $state('');
</script>
