<script>
import routes from '~/routes/index'
import Router, {location} from 'svelte-spa-router'
import Header from '~/components/Header.svelte'
import Footer from '~/components/Footer.svelte'
import {fade} from 'svelte/transition'
</script>

<Header />
{#key $location}
    <div in:fade>
      <Router 
        {routes} 
        restoreScrollState={true}/>
    </div>
{/key}
<Footer/>


