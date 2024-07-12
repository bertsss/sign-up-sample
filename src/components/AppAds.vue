<template>
    <div class="ads-container">
        <h3>Why Should You?</h3>

        <div class="items-wrapper">
            <div class="item">
                <div class="checkmark-circle">
                    <span class="checkmark"></span>
                </div>
                <p>USP 1</p>
            </div>

            <div class="item">
                <div class="checkmark-circle">
                    <span class="checkmark"></span>
                </div>
                <p>USP 2</p>
            </div>

            <div class="item">
                <div class="checkmark-circle">
                    <span class="checkmark"></span>
                </div>
                <p>USP 3</p>
            </div>
        </div>

        <div class="tips-wrapper">
            <p class="tips">Tips: password must be at least 8 characters and contain at least 1 capital letter and 1 number</p>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@import "@/assets/styles/variables";

.ads-container {
    border-radius: 20px;
    padding: 30px 20px;
    background-color: $light-yellow;
    border: 1px solid $bright-yellow;
    background: linear-gradient(165deg, $light-yellow 70%, $bright-yellow 30%);

    h3 {
        margin-bottom: 20px;
    }

    .items-wrapper {
        display: flex;
        flex-direction: column;
        margin-bottom: 25px;

        .item {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
            
            .checkmark-circle {
                display: flex;
                align-items: center;
                justify-content: center;
                width: 20px;
                height: 20px;
                border-radius: 50%;
                border: 2px solid $bright-yellow;
                position: relative;
                margin-right: 10px;
            }
    
            .checkmark {
                display: block;
                width: 4px;
                height: 8px;
                border: solid $bright-yellow;
                border-width: 0 2px 2px 0;
                transform: rotate(45deg);
            }
    
            p {
                color: #636262;
            }
        }

    }

    .tips-wrapper {
        border-radius: 10px;
        background-color: $white;
        border: 1px solid $bright-yellow;
        padding: 10px 20px;
    }
}
</style>