<template>
    <header class="site-header">
        <nav aria-label="Primary navigation" class="app-container py-4 lg:flex lg:items-center lg:justify-between">
            <div id="titleName" class="flex items-center justify-between gap-4">
                <RouterLink class="brand-mark text-xl font-black" to="/" @click="isMenuOpen = false">NETFLIXDEMO
                </RouterLink>
                <button
                    class="inline-flex h-10 w-10 items-center justify-center rounded-md border border-white/20 text-white lg:hidden"
                    type="button" :aria-expanded="isMenuOpen" aria-controls="mainNavigation"
                    aria-label="Toggle navigation" @click="isMenuOpen = !isMenuOpen">
                    <span aria-hidden="true">{{ isMenuOpen ? 'X' : 'Menu' }}</span>
                </button>
            </div>

            <div id="mainNavigation" class="mt-4 items-center gap-6 lg:mt-0 lg:flex lg:flex-1 lg:ml-10"
                :class="isMenuOpen ? 'flex flex-col items-start' : 'hidden'">
                <ul class="flex flex-col gap-3 text-sm font-medium text-zinc-300 lg:flex-row lg:items-center lg:gap-6">
                    <li>
                        <RouterLink class="nav-link" to="/" @click="isMenuOpen = false">Home</RouterLink>
                    </li>
                    <li>
                        <RouterLink class="nav-link" to="/search" @click="isMenuOpen = false">Search</RouterLink>
                    </li>
                    <li>
                        <RouterLink class="nav-link" to="/genres/Drama" @click="isMenuOpen = false">Drama</RouterLink>
                    </li>
                    <li>
                        <RouterLink class="nav-link" to="/genres/Comedy" @click="isMenuOpen = false">Comedy</RouterLink>
                    </li>
                </ul>

                <RouterLink class="button-outline lg:ml-auto" to="/watchlist" @click="isMenuOpen = false">
                    <span aria-hidden="true">♡</span>
                    <span>Watchlist</span>
                    <span class="badge-red">{{ '#0' }}</span>
                </RouterLink>
            </div>
        </nav>
    </header>
</template>

<script setup lang='ts'>
import { ref } from 'vue'
const isMenuOpen = ref(false)
</script>

<style></style>