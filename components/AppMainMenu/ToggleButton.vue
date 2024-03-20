<template>
    <button id="sidenav-button" type="button" :class="{ 'closed': closed }"> 
        <svg id="icon" xmlns="http://www.w3.org/2000/svg" width="26" height="26" viewBox="0 0 24 24">
            <path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" d="M3 6.001h18m-18 6h18m-18 6h18"/>
        </svg>
    </button>
</template>
<script lang="ts" setup>
const props = defineProps({
    closed: Boolean
});
</script>
<style lang="scss" scoped>
#sidenav-button {
    width: 50px;
    height: 50px;
    position: absolute;
    top: 2rem;
    right: 2rem;
    z-index: 1;
    background-color: $secondary-color;
    border: none;
    cursor: pointer;
    box-shadow: 0px 0px 18px 0px $tertiary-color;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 3px;
    transform: rotate(45deg);
    transition: ease-in-out 0.3s;

    &.closed {
        transform: rotate(135deg);
    }
    &:hover {
        background-color: $quaternary-color;
    }

    svg#icon {
        color: white;
        transform: rotate(-45deg);
    }
}
</style>