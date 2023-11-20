<script>
    let modalToggle = true;
    function isModalOpen() {
        modalToggle = !modalToggle;
    }
</script>

<div class="fixed left-20 bottom-20 grid gap-5">
    <div class="{modalToggle ? 'open' : ''} window">
        <ul>
            <li class="error">
                <p>
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                    Dicta cumque omnis, assumenda voluptates consequuntur et
                    dignissimos? Magni quaerat in ratione.
                </p>
                <div class="show_link-wrapper">
                    <a href="/" class="show_link">Показать</a>
                </div>
            </li>
            <li class="error">
                <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    Magni, modi.
                </p>
                <div class="show_link-wrapper">
                    <a href="/" class="show_link">Показать</a>
                </div>
            </li>
            <li class="warning">
                <p>Lorem ipsum dolor sit amet.</p>
                <div class="show_link-wrapper">
                    <a href="/" class="show_link">Показать</a>
                </div>
            </li>
        </ul>
    </div>
    <div class="button-wrapper">
        <!-- svelte-ignore a11y-no-static-element-interactions -->
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div on:click={isModalOpen} class="button">
            <div class="indicator-wrapper">
                <div class="indicator error">2</div>
                <div class="indicator warning">1</div>
            </div>
            <span class="button-label">В договоре есть ошибки!</span>
            <i class="material-symbols-outlined {modalToggle ? 'rotate' : ''}"
                >swap_vert</i
            >
        </div>
    </div>
</div>

<style lang="scss">
    .material-symbols-outlined {
        font-variation-settings: "FILL" 1, "wght" 400, "GRAD" 0, "opsz" 20;
    }

    .window {
        // margin-left: 0.5rem;
        max-width: 30rem /* 480px */;
        opacity: 0;
        pointer-events: none;
        user-select: none;
        transform: translateX(-2rem);
        transition: all 200ms ease-out 0s;
        box-shadow: $shadow;
        &.open {
            opacity: 1;
            pointer-events: all;
            user-select: auto;
            transform: translateX(0);
        }
        ul {
            display: grid;
            gap: 0.5rem /* 8px */;
            li {
                display: grid;
                gap: 0.5rem; /* 8px */
                padding: 0.75rem /* 12px */;
                color: white;
                border-radius: 0.375rem /* 6px */;
                box-shadow: $shadow;
                &.error {
                    // color: $red;
                    border-left-color: $red;
                    background: $red;
                }
                &.warning {
                    // color: $orange;
                    border-left-color: $orange;
                    background: $orange;
                }
                .show_link-wrapper {
                    display: flex;
                    justify-content: flex-end;
                    .show_link {
                        text-decoration-line: underline;
                        transition: opacity 100ms ease-in-out;
                        &:hover {
                            opacity: 0.5;
                        }
                    }
                }
            }
        }
    }

    .button-wrapper {
        display: flex;
        .button {
            display: flex;
            align-items: center;
            background: white;
            padding: 0.75rem /* 12px */;
            border-radius: 0.375rem /* 6px */;
            gap: 0.5rem /* 8px */;
            cursor: pointer;
            user-select: none;
            box-shadow: $shadow;
            .indicator-wrapper {
                display: flex;
                gap: 0.25rem /* 4px */;
                .indicator {
                    width: 24px;
                    height: 24px;
                    display: flex;
                    place-content: center;
                    border-radius: 0.25rem /* 4px */;
                    font-weight: bold;
                    color: white;
                    &.error {
                        background: $red;
                    }
                    &.warning {
                        background: $orange;
                    }
                }
            }
            .button-label {
                font-weight: 600;
            }
            i {
                display: flex;
                transition-property: all;
                transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
                transition-duration: 200ms;
                &.rotate {
                    rotate: 180deg;
                }
            }
        }
    }

    @keyframes shake {
        10%,
        30% {
            rotate: 15deg;
        }
        20% {
            rotate: -15deg;
        }
        50% {
            rotate: 0deg;
        }
    }

    @keyframes pulse {
        100% {
            scale: 2.5;
            opacity: 0;
        }
    }
</style>
