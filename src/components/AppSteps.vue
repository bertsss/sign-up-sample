<template>
    <div class="wrapper">
        <div class="steps-container">
            <ul class="progressbar">
                    <li data-before-content="1" :class="{'active': step === 1}"><p>Setup An Account</p></li>
                    <li data-before-content="2" :class="{'active': step === 2}"><p>Done!</p></li>
                </ul>
        </div>
    </div>
</template>

<script>
export default {
    props: ['step']
}
</script>

<style lang="scss" scoped>
@import "@/assets/styles/variables";

.steps-container {
    width: 100%;

    .progressbar {
        display: flex;
        justify-content: center;
        position: relative;
        z-index: 0;
        margin: 40px 0;

        li {
            list-style: none;
            display: inline-block;
            width: 50%;
            position: relative;
            text-align: center;
            font-weight: 500;

            &::after {
                content: "";
                display: block;
                position: absolute;
                width: 100%;
                height: 3px;
                background-color: $light-blue;
                top: 13px;
                left: -50%;
                z-index: -1;
            }

            &::before {
                content: attr(data-before-content);
                width: 22px;
                height: 22px;
                border: 3px solid $light-blue;
                border-radius: 100%;
                display: block;
                margin: 0 auto 16px auto;
                background-color: $light-blue;
                display: flex;
                justify-content: center;
                align-items: center;
                color: $gray;
            }

            &:first-child::after {
                content: none;
            }

            &.active {
                &::before {
                    border-color: $light-blue;
                    background-color: $blue;
                    color: $white;
                }
            }
        }
    }
}
</style>