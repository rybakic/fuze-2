<script>
    import Item from "./Item.svelte";

    export let name = "Название";
</script>

<div class="ItemGroup">
    <div class="heading">
        <span class="h3">{name}</span>
        <a href="/" class="more-button">Все</a>
    </div>
    <div class="item-list">
        <Item tSale tNew />
        <Item tVegan tSale />
        <Item tHot tNew />
        <Item tSale />
        <Item tNew />
    </div>
</div>

<style lang="scss">
    .ItemGroup {
        width: 100%;
        display: grid;
        gap: 1.25rem;
        margin-top: 1.25rem;
        .heading {
            display: flex;
            justify-content: space-between;
            align-items: center;
            .h3 {
                width: 280px;
                font-weight: 700;
                font-size: 1.375rem;
                text-overflow: ellipsis;
                text-wrap: nowrap;
                overflow: hidden;
            }
            .more-button {
                font-weight: 600;
                padding: 0.5rem 1rem;
                border-radius: $full;
                background: $gray-5-dark;
            }
        }
        .item-list {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 0.625rem;
        }
    }
</style>
