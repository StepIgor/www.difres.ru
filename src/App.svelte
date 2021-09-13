<script>
    import Header from "./header.svelte"
    import SearchBar from "./SearchBar.svelte"
    import SearchResultsContainer from "./SearchResultsContainer.svelte";

    let username = localStorage.getItem('username')
    let searchResultsContainer
    let searchBar

    function activateSearch(e) {
        searchResultsContainer.startSearch(e.detail.text)
    }

</script>

<div class="container">
    {#if username}
        <Header username={username}/>
    {:else}
        <Header/>
    {/if}
    <SearchBar bind:this={searchBar} on:startSearch={activateSearch}/>
    <SearchResultsContainer bind:this={searchResultsContainer}/>
</div>
