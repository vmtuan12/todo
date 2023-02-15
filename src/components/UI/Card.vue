<script setup>
</script>

<template>
    <div class="item">
        <div class="details">
            <div class="checked">
                <slot name="checked"></slot>
                <h4>
                    <slot name="index"></slot>
                </h4>
            </div>
            <div class="task">
                <div class="title">
                    <h2>
                        <slot name="heading"></slot>
                    </h2>
                </div>
                <div class="description">
                    <h3>
                        <slot name="info"></slot>
                    </h3>
                </div>
            </div>
            <div class="btn">
                <slot name="button"></slot>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .item {
        /* display: flex; */
        align-items: center;
        border-radius: 10px;
        margin: auto;
        width: 600px;
        min-height: 100px;
        box-shadow: 0 10px 20px rgba(0, 0, 0, 0.66);
        margin-top: 30px;
        background-color: white;
        transition: width 1s, height 2s, transform 2s;
        animation: card-appear 1s ease-in-out forwards;
    }
    .item:hover {
        width: 650px;
        /* transform: rotate(180deg) */
    }
    
    @keyframes card-appear {
    from {
        opacity: 0;
        transform: translateY(5rem);
    }
  
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

    .details {
        display: flex;
        justify-content: space-between;
        align-items: center;
        /* flex-basis: 0; */
    }

    .checked {
        margin-left: 30px;
        display: flex;
        gap: 10px;
    }
    .task {
        display: flex;
        flex-direction: column;
        max-width: 300px;
        padding: 5px;
        min-width: 400px;
    }
    .title {
        display: flex;
        height: fit-content;
        overflow: hidden;
    }
    .description {
        display: flex;
        overflow: hidden;
    }
    .btn {
        display: flex;
        margin-right: 20px;
    }

    h2 {
        font-weight: bold;
        font-size: 30px;
    }

    h4 {
        color: black;
        font-size: 1.5rem;
    }
</style>