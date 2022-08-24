
<script>
	import { page } from '$app/stores'

	$: active = $page.url.pathname;

    async function getMenuItems(){
    let menuItems = await fetch(`/docs.json`).then((res) => res.json());
    console.log(menuItems)

    for (var item of menuItems) {
        const url = `/${item.slug}.json`;
        const kategorieItems = await fetch(url).then((res) => res.json());
        item.subpages = kategorieItems;
    }

	
    return menuItems
    }

    const menuItems = getMenuItems();

</script>

<nav>

	<div class='menu'>
		<ol>

            <div>
                {#await menuItems}
                    <p>Loading...</p>
                {:then items}
                    {#each items as item}
                        <li>
                            <h2>{item.title}</h2>
                            <ol>
                                {#each item.subpages as page}
                                    <li class:active={active.startsWith('/'+page.slug)}>
                                            <a sveltekit:prefetch href="/{page.slug}/" on:click={()=>{active=page.slug}}>
                                                {page.title}
                                            </a>
                                    </li>
                                {/each}
                            </ol>
                        </li>
                    {/each}
                {:catch error}
                    <p style="color: red">{error.message}</p>
                {/await}
                </div>

		</ol>
	</div>

</nav>




<style type='scss'>
   
   .menu ol {
    // display: flex;
    list-style-type: none;
    // margin: 30px -10px;
    padding: 0;
    justify-content: center;
    

    li {
        
        a {
            padding: 10px;
        }

        &.active {
            background: grey;
            color: white;
        }
    }
   }
    
</style>
    