<template>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
        <div class="container">
            <router-link class="navbar-brand" :to="{name : 'home'}">King Of Bots</router-link>
            <div class="collapse navbar-collapse" id="navbarText">
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li class="nav-item">
                    <router-link :class="route_name === 'pk_index' ? 'nav-link active' : 'nav-link'"  aria-current="page" :to="{name : 'pk_index'}">对战</router-link>
                </li>
                <li class="nav-item">
                    <router-link :class="route_name === 'ranklist_index' ? 'nav-link active' : 'nav-link'" :to="{name : 'ranklist_index'}">对局列表</router-link>
                </li>
                <li class="nav-item">
                    <router-link :class="route_name === 'recode_index' ? 'nav-link active' : 'nav-link'" :to="{name : 'recode_index'}">排行榜</router-link>
                </li>
            </ul>
            <ul class="navbar-nav a">
                <li class="nav-item dropdown">
                <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                    wky
                </a>
                <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
                    <li>
                        <router-link :class="route_name === 'user_bot_index' ? 'dropdown-item active' : 'dropdown-item'" :to="{name : 'user_bot_index'}">我的Bot</router-link>
                    </li>
                    <li><hr class="dropdown-divider"></li>
                    <li><a class="dropdown-item" href="#">退出</a></li>
                </ul>
                </li>
            </ul>
            </div>
        </div>
    </nav>
</template>


<script>
import { computed } from 'vue'
import { useRoute } from 'vue-router'
export default {
    setup() {
        const route = useRoute()
        let route_name = computed(() => route.name)
        return {
            route_name
        }
    }
}
</script>

<style>
    .a {
        padding: 0 30px 0 0;
    }
</style>