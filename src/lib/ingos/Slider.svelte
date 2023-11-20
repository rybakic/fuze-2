<script>
    let modalToggle = false;
    function isModalOpen() {
        modalToggle = !modalToggle;
    }
</script>

<div
    class="main fixed transition-all duration-1000 {modalToggle
        ? '-left-0'
        : '-left-[25rem]'} bottom-10 grid"
>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <!-- svelte-ignore a11y-no-static-element-interactions -->
    <div on:click={isModalOpen} class="button">
        <span class="label">Сообщение</span>
        <div class="icon-wrapper">
            <div class="icon">
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

    <div class="window">
        <div class="list-wrapper">
            <ul class="list">
                <li class="error">
                    <p>
                        Lorem ipsum dolor sit amet consectetur, adipisicing
                        elit. Dolor vitae expedita temporibus at recusandae
                        impedit eligendi magni enim, repellendus aliquam.
                    </p>
                </li>
                <li class="error">
                    <p>
                        Lorem ipsum dolor sit amet consectetur adipisicing elit.
                        Harum, aspernatur?
                    </p>
                </li>
                <li class="warning">
                    <p>Lorem ipsum dolor sit amet.</p>
                </li>
                <li class="warning">
                    <p>
                        Lorem ipsum dolor sit amet consectetur, adipisicing
                        elit. Dolor vitae expedita temporibus at recusandae
                        impedit eligendi magni enim, repellendus aliquam.
                    </p>
                </li>
            </ul>
        </div>
    </div>
</div>

<style lang="scss">
    .material-symbols-outlined {
        font-variation-settings: "FILL" 0, "wght" 400, "GRAD" 0, "opsz" 20;
    }

    .button {
        display: flex;
        cursor: pointer;
        border-radius: 0.375rem /* 6px */;
        box-shadow: $shadow;
        .label {
            width: 25rem;
            background: $primary;
            display: grid;
            place-content: center;
            color: white;
            font-weight: 500;
            z-index: 100;
        }
        .icon-wrapper {
            position: relative;
            display: grid;
            place-content: center;
            background: white;
            // border: 2px solid $primary;
            border-left: 0;
            color: $primary;
            padding: 0.5rem /* 6px */;
            border-start-end-radius: 0.375rem /* 6px */;
            border-end-end-radius: 0.375rem /* 6px */;
            transition-property: all;
            transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
            transition-duration: 150ms;
            &:hover {
                background: $primary;
                color: white;
            }
            .icon {
                width: 1.5rem /* 24px */;
                height: 1.5rem /* 24px */;
                position: relative;
                i {
                    position: absolute;
                    &.bell {
                        transition-property: rotate, scale, opacity;
                        transition-timing-function: ease-in-out;
                        transition-duration: 200ms;
                        animation: shake 1s ease-in-out 0s infinite normal none;
                        &::before {
                            display: block;
                            content: "";
                            width: 7px;
                            height: 7px;
                            background: red;
                            position: absolute;
                            right: 0.125rem;
                            top: 0.125rem;
                            border-radius: 100%;
                        }
                        &.hide {
                            animation: none;
                            rotate: 360deg;
                            scale: 0;
                            opacity: 0;
                        }
                    }
                    &.close {
                        transition-property: rotate, scale, opacity;
                        transition-timing-function: ease-in-out;
                        transition-duration: 200ms;
                        &.hide {
                            rotate: 360deg;
                            scale: 0;
                            opacity: 0;
                        }
                    }
                }
            }
        }
    }

    .window {
        max-width: 25rem;
        background: white;
        border-bottom-right-radius: 0.375rem /* 6px */;
        border-bottom-left-radius: 0.375rem /* 6px */;
        box-shadow: $shadow;
        .list-wrapper {
            margin-top: 0.75rem /* 12px */;
            margin-bottom: 0.75rem /* 12px */;
            padding-left: 0.75rem /* 12px */;
            padding-right: 0.75rem /* 12px */;
            max-height: 20rem;
            overflow-y: auto;
            overflow-x: hidden;
            &::-webkit-scrollbar {
                width: 0.5rem /* 12px */;
            }
            &::-webkit-scrollbar-thumb {
                box-shadow: inset 0 0 0 10rem rgb(235, 235, 235);
                border-right: 0.25rem solid transparent;
            }
            .list {
                display: grid;
                gap: 0.75rem /* 12px */;
                li {
                    padding: 0.75rem /* 12px */;
                    border-radius: 0.375rem /* 6px */;
                    &.error {
                        color: $red;
                        background: $light_red;
                    }
                    &.warning {
                        color: $orange;
                        background: $light_orange;
                    }
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
</style>
