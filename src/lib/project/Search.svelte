<script></script>

<div class="wrapper">
    <div class="search">
        <div class="ico">
            <i class="material-symbols-outlined">search</i>
        </div>
        <input type="text" placeholder="Поиск" />
    </div>
</div>

<style lang="scss">
    .search {
        display: flex;
        background: $gray-5-dark;
        padding: 0.8125rem 1rem;
        border-radius: 0.5rem;
        .ico {
            display: flex;
        }
        input {
            padding-left: 0.625rem;
            background: transparent;
            width: 100%;
            outline: none;
            font-size: 1.125rem;
            &::placeholder {
                color: $default-light;
            }
        }
    }
</style>
