<script>
</script>

<header class="header">
    <a href="/" class="logo-btn">ЯКИТОРИЯ</a>
    <div class="wrapper">
        <a href="/" class="favorite-btn"
            ><i class="material-symbols-outlined fill">favorite</i></a
        >
        <a href="/" class="comment-btn flex p-3"
            ><i class="material-symbols-outlined fill">comment</i></a
        >
    </div>
</header>

<style lang="scss">
    .header {
        position: sticky;
        top: 0;
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 0.625rem 1.25rem;
        background: $gray-6-dark;
        .logo-btn {
            background: $red-light;
            font-weight: 600;
            font-size: 1.125rem;
            padding: 0.875rem 1.75rem;
            border-radius: 0.5rem;
        }
        .wrapper {
            display: flex;
            align-items: center;
            gap: 0.625rem;
            .favorite-btn {
                display: flex;
                padding: 0.8125rem;
                border-radius: 8px;
                background: $gray-5-dark;
            }
            .comment-btn {
                display: flex;
                padding: 0.8125rem;
                border-radius: 8px;
                background: $red-light;
            }
        }
    }
</style>
