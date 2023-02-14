<script setup>
</script>

<template>
    <div class="item">
        <div class="details">
            <div>
                <slot name="checked"></slot>
            </div>
            <div>
                <h2>
                    <slot name="heading"></slot>
                </h2>
            </div>
            <!-- <h5>
                <slot name="info"></slot>
            </h5> -->
            <div>
                <slot name="button"></slot>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .item {
        display: flex;
        border-radius: 10px;
        border: 1.5px solid black;
        margin: auto;
        max-width: 600px;
        height: fit-content;
    }

    .details {
        display: flex;
        justify-content: space-around;
        align-items: center;
    }

    h2 {
        font-weight: bold;
        font-size: 30px;
    }
    h5 {
        font-size: 15px;
    }
</style>