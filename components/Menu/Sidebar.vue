<template>
    <div class="sidebar">
        <div class="sidebar-backdrop" @click="closeSidebarPanel" v-if="isPanelOpen"></div>
        <transition name="slide">
            <div v-if="isPanelOpen"
                 class="sidebar-panel">
                <slot></slot>
            </div>
        </transition>
    </div>
</template>
<script>
    import { store, mutations } from './store.js'

    export default {
        methods: {
            closeSidebarPanel: mutations.toggleNav
        },
        computed: {
            isPanelOpen() {
                return store.isNavOpen
            }
        }
    }
</script>
<style>
    .slide-enter-active,
    .slide-leave-active
    {
        transition: transform 0.6s ease;
    }

    .slide-enter,
    .slide-leave-to {
        transform: translateX(-100%);
        transition: all 150ms ease-in 0s
    }

    .sidebar-backdrop {
        background-color: rgba(0,0,0,.6);
        width: 100vw;
        height: 100vh;
        position: fixed;
        top: 0;
        cursor: pointer;
        z-index: 5;
        left: 64px;
    }

    .sidebar-panel {
        overflow-y: auto;
        background-color: black;
        position: fixed;
        left: 64px;
        top: 0;
        height: 100vh;
        z-index: 999;
        padding: 3rem 20px 2rem 20px;
        width: 52%;
        padding-top: 15%;
    }
    @media screen and (min-width: 768px) and (max-width: 1023px) {
      .sidebar-panel{
      width: 100%;
      height: 100%;
    }
    }
</style>
