<div style="min-width: 100px;">
  <Button onclick={() => menu.setOpen(true)}>
    <Label>Open Menu</Label>
  </Button>
  <Menu bind:this={menu}>
    <List>
      <SelectionGroup>
        {#each ['Red', 'Green', 'Blue'] as item}
          <Item
            onSMUIAction={() => (selected1 = item)}
            selected={selected1 === item}
          >
            <SelectionGroupIcon>
              <i class="material-icons">check</i>
            </SelectionGroupIcon>
            <Text>{item}</Text>
          </Item>
        {/each}
      </SelectionGroup>
      <Separator />
      <SelectionGroup>
        {#each ['Small', 'Medium', 'Large'] as item}
          <Item
            onSMUIAction={() => (selected2 = item)}
            selected={selected2 === item}
          >
            <SelectionGroupIcon>
              <i class="material-icons">check</i>
            </SelectionGroupIcon>
            <Text>{item}</Text>
          </Item>
        {/each}
      </SelectionGroup>
      <Separator />
      <Item onSMUIAction={() => (clicked = 'Save for Later')}>
        <Text>Save for Later</Text>
      </Item>
    </List>
  </Menu>
</div>

<pre class="status">Selection 1: {selected1}</pre>
<pre class="status">Selection 2: {selected2}</pre>
<pre class="status">Clicked: {clicked}</pre>

<script lang="ts">
  import Menu, { SelectionGroup, SelectionGroupIcon } from '@smui/menu';
  import List, { Item, Separator, Text } from '@smui/list';
  import Button, { Label } from '@smui/button';

  let menu: Menu;
  let clicked = $state('nothing yet');
  let selected1 = $state('Red');
  let selected2 = $state('Small');
</script>
