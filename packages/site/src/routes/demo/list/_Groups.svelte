<div>
  <Group>
    <Subheader>Actors</Subheader>
    <List class="demo-list">
      <Item onSMUIAction={() => (clicked = 'Bruce Willis')}>
        <Text>Bruce Willis</Text>
      </Item>
      <Item onSMUIAction={() => (clicked = 'Tom Hanks')}>
        <Text>Tom Hanks</Text>
      </Item>
      <Item onSMUIAction={() => (clicked = 'Jack Nicholson')}>
        <Text>Jack Nicholson</Text>
      </Item>
      <Item onSMUIAction={() => (clicked = 'Leonardo DiCaprio')}>
        <Text>Leonardo DiCaprio</Text>
      </Item>
      <Item onSMUIAction={() => (clicked = 'Matt Damon')}>
        <Text>Matt Damon</Text>
      </Item>
    </List>
    <Subheader>Books</Subheader>
    <List class="demo-list">
      <Item onSMUIAction={() => (clicked = 'To Kill a Mockingbird')}>
        <Text>To Kill a Mockingbird</Text>
      </Item>
      <Item onSMUIAction={() => (clicked = 'The Great Gatsby')}>
        <Text>The Great Gatsby</Text>
      </Item>
      <Item onSMUIAction={() => (clicked = '1984')}>
        <Text>1984</Text>
      </Item>
      <Item onSMUIAction={() => (clicked = 'Catch-22')}>
        <Text>Catch-22</Text>
      </Item>
      <Item onSMUIAction={() => (clicked = "Alice's Adventures in Wonderland")}>
        <Text>Alice's Adventures in Wonderland</Text>
      </Item>
    </List>
  </Group>
</div>

<pre class="status">Clicked: {clicked}</pre>

<script lang="ts">
  import List, { Group, Item, Subheader, Text } from '@smui/list';

  let clicked = $state('nothing yet');
</script>

<style>
  * :global(.demo-list) {
    max-width: 600px;
    border-left: 1px solid
      var(--mdc-theme-text-hint-on-background, rgba(0, 0, 0, 0.1));
  }
</style>
