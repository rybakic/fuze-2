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
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta
                cumque omnis, assumenda voluptates consequuntur et dignissimos?
                Magni quaerat in ratione.
            </li>
            <li class="error">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Magni,
                modi.
            </li>
            <li class="warning">Lorem ipsum dolor sit amet.</li>
        </ul>
    </div>
    <div class="button-wrapper">
        <!-- svelte-ignore a11y-no-static-element-interactions -->
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div on:click={isModalOpen} class="button">
            <div class="w-[24px] h-[24px] relative">
                <i
                    class="material-symbols-outlined bell {modalToggle
                        ? 'hide'
                        : ''}">notifications</i
                >
                <i
                    class="material-symbols-outlined close {modalToggle
                        ? ''
                        : 'hide'}">close</i
                >
            </div>
        </div>
    </div>
</div>

<style lang="scss">
    .material-symbols-outlined {
        font-variation-settings: "FILL" 1, "wght" 400, "GRAD" 0, "opsz" 20;
    }

    .window {
        // margin-left: 0.5rem /* 8px */;
        max-width: 30rem /* 480px */;
        opacity: 0;
        pointer-events: none;
        user-select: none;
        transform: translateX(-2rem);
        transition: all 200ms ease-out 0s;
        &.open {
            opacity: 1;
            pointer-events: all;
            user-select: auto;
            transform: translateX(0);
        }
        ul {
            display: grid;
            gap: 0.75rem /* 12px */;
            li {
                border-left-width: 4px;
                padding: 0.75rem /* 12px */;
                border-start-end-radius: 0.375rem /* 6px */;
                border-end-end-radius: 0.375rem /* 6px */;
                box-shadow: $shadow;
                &.error {
                    // color: $red;
                    border-left-color: $red;
                    background: $light_red;
                    color: $red;
                }
                &.warning {
                    // color: $orange;
                    border-left-color: $orange;
                    background: $light_orange;
                    color: $orange;
                }
            }
        }
    }

    .button-wrapper {
        display: flex;
        .button {
            position: relative;
            cursor: pointer;
            background: $primary;
            display: grid;
            place-content: center;
            color: white;
            padding: 1rem /* 16px */;
            border-radius: 100%;
            &::before,
            &::after {
                content: "";
                position: absolute;
                width: 100%;
                height: 100%;
                background-color: $primary_pulse;
                border-radius: 100%;
                z-index: -1;
                opacity: 0.7;
            }
            &::before {
                animation: pulse 2s ease-out infinite;
            }
            &::after {
                animation: pulse 2s 1s ease-out infinite;
            }
            i {
                position: absolute;
                transition: all 200ms ease-in-out;
                &.bell {
                    animation: shake 1s ease-in-out 0s infinite normal none;
                    &.hide {
                        animation: none;
                        rotate: 360deg;
                        scale: 0;
                        opacity: 0;
                    }
                }
                &.close {
                    &.hide {
                        rotate: 360deg;
                        scale: 0;
                        opacity: 0;
                    }
                }
                &.bell::before {
                    display: block;
                    content: "";
                    width: 7px;
                    height: 7px;
                    background: red;
                    position: absolute;
                    right: 0;
                    top: 0;
                    border-radius: 100%;
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
