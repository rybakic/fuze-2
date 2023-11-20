<script>
    import Bell from "$lib/ingos/Bell.svelte";
    import Button from "$lib/ingos/Button.svelte";
    import Slider from "$lib/ingos/Slider.svelte";
    import Header from "$lib/project/Header.svelte";
    import Search from "$lib/project/Search.svelte";
    import ItemList from "$lib/project/ItemList/ItemList.svelte";
    import CartBtn from "$lib/project/CartBtn.svelte";
</script>

<Header />
<CartBtn />
<div class="wrapper">
    <Search />
    <ItemList name="Лучшее предложение" />
    <ItemList name="Хот-доги и сендвичи" />
</div>

<!-- <div class="bg-gray-100 h-screen" />
<div class="bg-red-100 h-screen" />
<div class="bg-yellow-100 h-screen" />
<div class="bg-green-100 h-screen" />
<div class="bg-blue-100 h-screen" /> -->

<!-- <Bell /> -->

<!-- <Button /> -->

<!-- <Slider /> -->

<style lang="scss">
    .wrapper {
        padding: 0 1.25rem;
        margin-top: 3.125rem;
        margin-bottom: 1.25rem;
    }
</style>
