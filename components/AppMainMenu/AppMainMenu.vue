<template>
    <div class="sidenav-container">
        <nav id="sidenav" :class="{ 'closed': !menuOpeningState }">
            <ToggleButton 
                @click="toggleMenuOpeningState"
                :closed="menuOpeningState"
            />
            <div id="sidenav__body" :class="{'closed': !menuOpeningState}">

            </div>
            <div id="sidenav__footer" :class="{'closed': !menuOpeningState}">

            </div>  
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
        &__body {
            position: fixed;
            top: -20dvh;
            left: -220px;
            width: 400px;
            height: 150dvh;
            background-color: $secondary-color;
            transform: rotate(12deg);
            box-shadow: 0px 0px 18px 0px $tertiary-color;
            transition: ease-in-out 0.4s;

            &.closed {
                left: -150dvw;
                top: -50dvh;
            }
        }

        &__footer {
            position: fixed;
            bottom: -324px;
            left: -222px;
            width: 400px;
            height: 100dvh;
            background-color: $secondary-color;
            transform: rotate(-26deg);
            box-shadow: 0px 0px 18px 0px $tertiary-color;
            transition: ease-in-out 0.7s;

            &.closed {
                left: -100%;
                bottom: -50%;
            }
        }
    }
}

</style>