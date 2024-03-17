<template>
    <div class="sidenav-container">
        <ToggleButton 
            @click="toggleMenuOpeningState"
            :closed="menuOpeningState"
        />
        <nav id="sidenav" :class="{ 'closed': !menuOpeningState }">
            
        </nav>
    </div>
</template>
<script lang="ts" setup>
import ToggleButton from './ToggleButton.vue';

const menuOpeningState = ref(false);

const toggleMenuOpeningState = () => {
    menuOpeningState.value = !menuOpeningState.value;
};
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

        &.closed {
            left: -600px;
        }
    }
}

</style>