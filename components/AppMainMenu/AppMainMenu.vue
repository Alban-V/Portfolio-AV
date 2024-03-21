<template>
    <div class="sidenav-container">
        <nav id="sidenav">
            <ToggleButton 
                @click="toggleMenuOpeningState"
                :closed="menuOpeningState"
            />
            <div id="sidenav__body" :class="{'closed': !menuOpeningState}">
                <div id="sidenav__body__background" :class="{ 'closed': !menuOpeningState }"></div >
                <div id="sidenav__body__wrapper" :class="{ 'closed': !menuOpeningState }" >
                    <h1>{{ pageTitle }}</h1>
                    
                </div>
            </div>
            <div id="sidenav__footer" :class="{'closed': !menuOpeningState}">
                <div id="sidenav__footer__background" :class="{ 'closed': !menuOpeningState }"></div>
              
            </div>
        </nav>
    </div>
</template>
<script lang="ts" setup>
import ToggleButton from './ToggleButton.vue';

const menuOpeningState: Ref<boolean> = ref(false);
const pageTitle: string = "Alban Vincent";

const toggleMenuOpeningState = () => {
    menuOpeningState.value = !menuOpeningState.value;
};

onMounted(() => {
    setTimeout(() => {
        menuOpeningState.value = true;
    }, 1000);
});
</script>
<style lang="scss" scoped>
.sidenav-container {
    position: relative;

    #sidenav {

        &__body {
            position: relative;
            width: 250px;
            height: 100dvh;
            filter: drop-shadow(0 0 0.75rem $tertiary-color);
            transition: all 1s ease-in-out;
            left: 0;

            &.closed {
                left: -200dvw;
            }

            &__background {
                position: absolute;
                left: -100%;
                top: -50%;
                height: 150vh;
                width: 550px;
                background-color: $secondary-color;
                clip-path: polygon(0 0, 100% 25%, 50% 100%, 0 100%);
            }

            &__wrapper {
                width: 100%;
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                position: absolute;
                top: 10px;
                color: white;
            }

            
        }

        &__footer {
            position: relative;
            width: 300px;
            height: 100dvh;
            filter: drop-shadow(0 0 0.75rem $tertiary-color);
            
            &__background {
                position: absolute;
                left: -100%;
                top: -50%;
                height: 150vh;
                width: 550px;
                background-color: $secondary-color;
                clip-path: polygon(0 0, 100% 25%, 50% 100%, 0 100%);
                transition: all 0.3s ease-in-out;
                z-index: 1;
                transition: all 0.5s ease-in-out;

                &.closed {
                    left: -200dvw;
                }
            }
        }
    }
}

</style>