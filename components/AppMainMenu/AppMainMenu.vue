<template>
    <div class="sidenav-container">
        <ToggleButton/>
        <nav id="sidenav">
            
        </nav>
    </div>
</template>
<script setup>
import ToggleButton from './ToggleButton.vue';
</script>
<style lang="scss" scoped>
.sidenav-container {
    position: relative;

    #sidenav {
        width: 315px;
        height: 94dvh;
        position: fixed;
        top: 50%;
        left: -120px;
        background-color: $secondary-color;
        box-shadow: 0px 0px 18px 0px $tertiary-color;
        border-radius: 0 1.3rem 1.3rem 0;
        transform: skew(-5deg) translate(0, -50%);
    }
}

</style>