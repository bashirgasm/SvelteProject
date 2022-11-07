<script lang="ts">
  export let recipients;
    import     AuditTable from 'components/AuditTable.svelte';

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
/* <script lang="ts">
  import { groupBy } from 'lodash-es'
  import DateDisplay from 'components/DateDisplay.svelte'
  import TimeDisplay from 'components/TimeDisplay.svelte'
  import RecipientsDisplay from 'components/RecipientsDisplay.svelte'
  import type { Email } from 'types/Email'

  export let emails: Email[]

  const emailsByDate = groupBy<Email>(emails, ({ datetime }) =>
    new Date(datetime).toLocaleDateString()
  )
  // Convert into an array of arrays based on date sent
  const emailGroupsByDate = Object.entries(emailsByDate).map(val => val[1])
</script>

*/

