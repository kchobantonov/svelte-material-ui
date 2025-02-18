<svelte:head>
  <title>Common - SMUI</title>
</svelte:head>

<section>
  <h2>Common</h2>
  <p>A common Label and Icon, helper utilities, and elemental components.</p>

  <h5>Installation</h5>

  <pre class="demo-spaced">npm i -D @smui/common</pre>

  <h5>Demos</h5>

  <Demo component={CommonLabelIcon} file="common/_CommonLabelIcon.svelte">
    Common Label and Icon
    {#snippet subtitle()}
      The common label and icon are also exported from each package that uses
      them.
    {/snippet}
  </Demo>

  <Demo component={SmuiElement} file="common/_SmuiElement.svelte">
    SmuiElement Component
    {#snippet subtitle()}
      Many SMUI components let you customize which DOM element is used to render
      them. This is done with the SmuiElement component.
    {/snippet}
  </Demo>

  <Demo component={Svg} file="common/_Svg.svelte">
    Svg Elements
    {#snippet subtitle()}
      In the SMUI components that let you customize which DOM element is used to
      render them, you can use the "svg" tag to render an SVG.
    {/snippet}
  </Demo>

  <h4>Helper Utilities</h4>

  <Demo component={ClassMap} file="common/_ClassMap.svelte">
    Class Map
    {#snippet subtitle()}
      Build a class string from a map of class names to conditions. This is
      useful when you need to add classes to a component, since Svelte's
      "class:" directives don't work on components. (It's also useful for
      actions that take <code>addClass</code> and <code>removeClass</code> functions.)
    {/snippet}
  </Demo>

  <Demo component={Dispatch} file="common/_Dispatch.svelte">
    Dispatch
    {#snippet subtitle()}
      Dispatch a custom event. This differs from Svelte's component event
      system, because these events require a DOM element as a target, can bubble
      (and do by default), and are cancelable with <code
        >event.preventDefault()</code
      >. All SMUI events are dispatched with this.
    {/snippet}
  </Demo>

  <Demo
    component={ExcludeAndPrefixFilter}
    files={[
      'common/_ExcludeAndPrefixFilter.svelte',
      'common/_ExcludeAndPrefixFilterComponent.svelte',
    ]}
  >
    Exclude and Prefix Filter
    {#snippet subtitle()}
      Exclude differs from normal <code>omit</code> functions by also excluding all
      properties that begin with a given string if that string ends with "$". Prefix
      Filter filters an object for only properties with a certain prefix. They are
      usually used together to allow props to be given to multiple elements within
      a component.
    {/snippet}
  </Demo>

  <Demo
    component={UseActions}
    files={[
      'common/_UseActions.svelte',
      'common/_UseActionsComponent.svelte',
      'common/_UseActionsPannable.ts',
      'common/_UseActionsSwipeable.ts',
      'common/_UseActionsTappable.ts',
    ]}
  >
    Use Actions
    {#snippet subtitle()}
      An action that takes actions and runs them on the element. Used to allow
      actions on components, and forward actions from one component to another,
      until the ultimate component finally renders the DOM element.
    {/snippet}
  </Demo>

  <Demo component={Announce} file="common/_Announce.svelte">
    Announce
    {#snippet subtitle()}
      A function that announces a string of text to users who are using a screen
      reader.
    {/snippet}
  </Demo>

  <h4>Other Components</h4>

  <Demo
    component={ClassAdder}
    files={['common/_ClassAdder.svelte', 'common/_ClassAdderComponent.ts']}
  >
    Class Adder
    {#snippet subtitle()}
      Use this to make a ClassAdder component.
    {/snippet}
  </Demo>
</section>

<script lang="ts">
  import Demo from '$lib/Demo.svelte';

  import CommonLabelIcon from './_CommonLabelIcon.svelte';
  import SmuiElement from './_SmuiElement.svelte';
  import Svg from './_Svg.svelte';
  import ClassMap from './_ClassMap.svelte';
  import Dispatch from './_Dispatch.svelte';
  import ExcludeAndPrefixFilter from './_ExcludeAndPrefixFilter.svelte';
  import UseActions from './_UseActions.svelte';
  import Announce from './_Announce.svelte';
  import ClassAdder from './_ClassAdder.svelte';
</script>
