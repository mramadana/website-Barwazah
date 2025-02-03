<template>
    <div class="defaultLayout">
        <div class="container">
            
            <header class="header" :class="headerClass">
                <div class="nav-header">
                    <div class="inner">
                        <nuxtLink to="/" class="logo btn-login">
                            <img
                                src="@/assets/images/logo.svg"
                                alt="logo"
                            />
                        </nuxtLink>
                        <ul
                            class="nav-links"
                            :class="{ active: navLinksActive }"
                        >
                            <li>
                                <NuxtLink to="#banner" class="link">
                                    {{ $t("Home.home") }}
                                </NuxtLink>
                            </li>

                            <li>
                                <NuxtLink to="#assistant" class="link">
                                    المساعد التسويقي
                                </NuxtLink>
                            </li>

                            <li>
                                <NuxtLink to="#Features" class="link">
                                    المميزات
                                </NuxtLink>
                            </li>

                            <li>
                                <NuxtLink to="#Services" class="link">
                                    الخدمات
                                </NuxtLink>
                            </li>

                            <li>
                                <NuxtLink to="#packages" class="link">
                                    الباقات
                                </NuxtLink>
                            </li>
                        </ul>

                        <div class="left">

                            <nuxt-link class="btn-login" to="/Auth/login">
                                <img src="@/assets/images/user-img.svg" alt="user-img" class="user-img">
                            </nuxt-link>
                            <button
                                class="nav-btn"
                                @click="handleClick"
                                :class="{ active: navBtnActive }"
                            >
                                <span></span><span></span><span></span>
                            </button>
                            <div
                                class="nav-overlay"
                                @click="handleOverlayClick"
                                :class="{ show: navOverlayShow }"
                            ></div>
                        </div>
                    </div>
                </div>
            </header>
        </div>

    </div>
</template>

<script>

export default {
    data() {
        return {
            htmlLang: "",
            navBtnActive: false,
            navLinksActive: false,
            navOverlayShow: false,
            isActive: false,
        };
    },

    methods: {

        handleClick() {
            this.navBtnActive = true;
            this.navLinksActive = true;
            this.navOverlayShow = true;
        },

        handleOverlayClick() {
            this.navBtnActive = false;
            this.navLinksActive = false;
            this.navOverlayShow = false;
        },
    },

    watch: {
    // Watch for changes in the route
    
    $route(to, from) {
      // Handle the event here
      console.log("Route changed:", to, from);
      this.handleOverlayClick();
    },
  },

    async mounted() {
        let sessionKey = localStorage.getItem("locale");

        window.sessionKey = localStorage.getItem("locale");
        if (sessionKey) {
            this.chageDir(localStorage.getItem("locale"));
        }
    },

    computed: {
        headerClass() {
            return {
                "add-margin": this.shouldAddMarginBottom,
            };
        },
        shouldAddMarginBottom() {
            // Check if the current route is not the home page
            console.log("updated is Done");
            return this.$route.path !=="/";
        },
    },
};
</script>

<style lang="scss">
.add-margin {
    margin-bottom: 40px;
}
.defaultLayout {
    position: sticky;
    top: 0;
    z-index: 1000;
}
</style>
