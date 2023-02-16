<script setup>
</script>

<template>
    <div class="item">
        <div class="input">
            <slot name="inputTitle"></slot>
            <slot name="inputDescription"></slot>
        </div>
        <div class="btn">
            <slot name="button"></slot>
        </div>
        <div class="dropdown">
            Style
            <div class="dropdown-content">
                <p>ab</p>
                <p>vab</p>
                <p>asd</p>
            </div>
        </div>
    </div>
    
</template>

<style scoped>
    .item {
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 15px 0px;
        width: 600px;
        height: 100px;
        border-radius: 10px;
        /* border: 1.5px solid black; */
        margin: auto;
        margin-top: 2rem;
        background-color: whitesmoke;
        box-shadow: 0 10px 20px rgba(0, 0, 0, 0.66);
        gap: 10px;
        transition: width 1s, height 1s, transform 2s;
        animation: card-appear 1s ease-in-out forwards;
        position: relative;
        z-index: 10;
        /* transition ko hoat dong neu co animation, height ko co transition */
    }

    .item:hover {
        width: 645px;
        height: 120px;
        /* transform: rotate(180deg) */
    }

    @keyframes card-appear {
        from {
            opacity: 0;
            transform: translateY(1rem);
        }
    
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    .dropdown::before {
        /* display: inline-block; */
        border: 1.5px solid black;
        padding: 10px;
    }

    .dropdown::before:hover {
        transform: scaleX(1);
        transform-origin: left;
    }
    .dropdown-content {
        display: none;
        position: absolute;
        background-color: #f9f9f9;
        min-width: 160px;
        box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
        padding: 12px 16px;
    }
    
    .dropdown:hover .dropdown-content {
        display: block;
        animation: dropdown-appear 1s ease-out forwards;
    }
    @keyframes dropdown-appear {
        from {
            opacity: 0;
            transform: translateY(2rem);
        }
    
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }
    .dropdown-content p {
        border: 1.5px solid black;
        margin-top: 5px;
        text-indent: 5px;
    }

    .input {
        display: flex;
        gap: 10px;
    }

</style>