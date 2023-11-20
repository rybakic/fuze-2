<script>
    export let tNew = false;
    export let tSale = false;
    export let tHot = false;
    export let tVegan = false;
</script>

<a href="/" class="Item">
    <!-- svelte-ignore a11y-missing-attribute -->
    <div class="image">
        <img src="panazia.jpg" />
        <div class="wrapper">
            <div class="tags">
                {#if tNew === true}
                    <div class="wrapper">
                        <div class="tag new">НОВИНКА</div>
                    </div>
                {/if}
                {#if tSale === true}
                    <div class="wrapper">
                        <div class="tag sale">СКИДКА</div>
                    </div>
                {/if}
                {#if tHot === true}
                    <div class="wrapper">
                        <div class="tag hot">ОСТРОЕ</div>
                    </div>
                {/if}
                {#if tVegan === true}
                    <div class="wrapper">
                        <div class="tag vegan">БЕЗ МЯСА</div>
                    </div>
                {/if}
            </div>
        </div>
    </div>
    <div class="name">Паназиатский с креветками и манго</div>
    <div class="wrapper">
        <div class="text">
            <h3>700.00 ₽</h3>
            <span>350 Г.</span>
        </div>
        <div class="add-btn"><i class="material-symbols-outlined">add</i></div>
    </div>
</a>

<style lang="scss">
    .Item {
        padding: 0.625rem;
        background: $gray-5-dark;
        border-radius: 1.5rem;
        box-shadow: $box-shadow;
        display: grid;
        gap: 0.75rem;
        .image {
            position: relative;
            img {
                border-radius: 1rem;
            }
            .tags {
                position: absolute;
                right: 0.3125rem;
                top: 0.3125rem;
                text-align: end;
                display: flex;
                flex-direction: column;
                gap: 0.3125rem;
                .wrapper {
                    display: flex;
                    justify-content: end;
                    .tag {
                        font-size: 0.625rem;
                        font-weight: 600;
                        padding: 0.25rem 0.5rem;
                        border-radius: 0.25rem;
                        transform: rotate(5deg);
                        &.new {
                            background: $blue-light;
                        }
                        &.sale {
                            background: $red-light;
                        }
                        &.hot {
                            background: $orange-light;
                        }
                        &.vegan {
                            background: $green-light;
                        }
                    }
                }
            }
        }
        .name {
            font-weight: 700;
            font-size: 1rem;
            display: -webkit-box;
            /* LINE CLAMP */
            -webkit-line-clamp: 2;
            -webkit-box-orient: vertical;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        .wrapper {
            display: flex;
            align-items: center;
            justify-content: space-between;
            .text {
                h3 {
                    font-weight: 700;
                    font-size: 1rem;
                }
                span {
                    font-weight: 400;
                    font-size: 0.875rem;
                    color: $gray-light;
                }
            }
            .add-btn {
                display: flex;
                border-radius: $full;
                padding: 0.75rem;
                background: $gray-3-dark;
            }
        }
    }
</style>
