<script setup>
</script>

<template>
    <div class="item">
        <div class="details">
            <div class="checked">
                <slot name="checked"></slot>
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
            <div>
                <slot name="button"></slot>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .item {
        
        align-items: center;
        border-radius: 10px;
        border: 1.5px solid black;
        margin: auto;
        max-width: 600px;
        background-color: whitesmoke;
        box-shadow: 0 2px 8px rgba(0, 0, 0, 0.66);
        margin-top: 10px;
        background-color: white;
        animation: card-appear 1s ease-in-out forwards;
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
        justify-content: space-around;
        align-items: center;
    }

    .task {
        display: flex;
        flex-direction: column;
        width: auto;
    }
    .title {
        display: flex;
        height: fit-content;
    }
    .description {
        display: flex;
    }

    h2 {
        font-weight: bold;
        font-size: 30px;
    }
</style>