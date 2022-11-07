<script lang="ts">
  export let recipients;
    import RecipientsDisplay  from './AuditTable.svelte';
</script>
<div class="recipients">
  <h2>{ recipients }</h2>
  <RecipientsDisplay recipients={recipients}/>
</div>
<main>
  <div class = "items">
    {#each inventory as item}
      <Item item={item}/>
    {/each}
  </div>

  <p>There are { $itemsInCart } items in your cart.</p>
  <p>Cart total: ${ $totalPrice }</p>
  <p>Cart contents:</p>
        
  <ol>
    {#each $cartContents as item}
      <li>{item}</li>
    {/each}
  </ol>
</main>
