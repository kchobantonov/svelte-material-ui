<Slider
  range
  bind:start={valueStart}
  bind:end={valueEnd}
  min={0}
  max={10}
  step={1}
  discrete
  tickMarks
  input$aria-label="Range slider"
/>

<pre class="status">Value: {valueStart} - {valueEnd}</pre>

<script lang="ts">
  import Slider from '@smui/slider';

  let valueStart = $state(4);
  let valueEnd = $state(6);
</script>
