<div class="card-display">
  <div class="card-container">
    <Card>
      <Content component={List}>
        <Item onclick={() => clicked++}>
          <Text>A card with a list as content.</Text>
        </Item>
        {#each [...Array(5)].map((_v, i) => i + 1) as item}
          <Item onclick={() => clicked++}>
            <Text>Item #{item}</Text>
          </Item>
        {/each}
      </Content>
    </Card>
  </div>
</div>

<pre class="status">Clicked: {clicked}</pre>

<script lang="ts">
  import Card, { Content } from '@smui/card';
  import List, { Item, Text } from '@smui/list';

  let clicked = $state(0);
</script>
