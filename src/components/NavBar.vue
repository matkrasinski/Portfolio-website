<template>
    <nav id="navbar">
        <div class="logo-container">
            <a href="" >
                <img src=".//../assets/logo.svg" alt="logo"/>
            </a>
        </div>
        <div id="burger-menu" href="" onclick="this.classList.toggle('change')" @click="showPopup()">
            <div class="first-bar"></div>
            <div class="second-bar"></div>
            <div class="third-bar"></div>
        </div>
        <nav id="burger-popup">
            <ol id="popup-list">
                <li class="bp-item"><a>About me</a></li>
                <li class="bp-item"><a>Projects</a></li>
                <li class="bp-item"><a>Interests</a></li>
                <li class="bp-item"><a>Goals</a></li>
            </ol>
        </nav>
    </nav>
</template>

<script>
export default {
    data() {
        return {
            isMobile: false,
            burgerClicked: false,
            windowWidth: window.innerWidth
        }
    },
    methods: {
        showPopup() {
            let popup = document.getElementById("burger-popup")
            let list = document.getElementById("popup-list")
            let items = list.getElementsByTagName("a")
            if (popup.style.opacity !== "1") {
                popup.style.transition = "1s";
                popup.style.opacity = "1"
                console.log(this.isMobile)
                if (this.isMobile) {
                    popup.style.width = "80%"
                    // popup.style.height = "100vh"
                } else {
                    popup.style.width = "25%"
                }
                for(let i = 0; i < items.length; i++) {
                        items[i].style.opacity = "1"
                    }
            } else {
                popup.style.width = "0"
                popup.style.opacity = "0"
                for(let i = 0; i < items.length; i++) {
                    items[i].style.opacity = 0
                }
            }
        }
    },
    mounted() {
        this.windowWidth = window.innerWidth;
        if (this.windowWidth > 440) {
            this.isMobile = false;
        } else {
            this.isMobile = true;
        }
        let lastScrollTop = 0;
        let navbar = document.getElementById("navbar");
        window.addEventListener("scroll", function() {
            let scrollTop = this.window.pageYOffset || this.document.documentElement.scrollTop;
            if (scrollTop > lastScrollTop) {
                navbar.style.top = "-80px"
            } else {
                navbar.style.top = "0";
            }
            lastScrollTop = scrollTop;
        })
    }
}

</script>

<style>
    #navbar {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 80px;
        padding: 0 200px;
        box-sizing: border-box;
        display: flex;
        justify-content: space-between;
        align-items: center;
        transition: 0.5s;
        backdrop-filter: blur(20px);
        box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
    }
    .menu-container {
        position: absolute;
        overflow: hidden;
        right: 30px;
    }
    ol a {
        padding-right: 8vw;
        font-size: 100%
    }

    .logo-container {
        overflow: hidden;
        float:left;
    }
    a img {
        position: absolute;
        top: 2%;
        left: 0;
        width: 10vw;
        height: 10vh;
    }

    #burger-menu {
        position: absolute;
        right: 10%;
        display: inline-block;
        cursor: pointer;
    }

    .first-bar, .second-bar, .third-bar {
        width: 20px;
        height: 2px;
        background-color: black;
        margin: 6px 0;
        transition: 0.4s;
        border-radius: 15px;
    }

    .change .first-bar {
        transform: translate(0, 8px) rotate(-45deg) ;
    }
    .change .second-bar {
        opacity: 0;
    }
    .change .third-bar {
        transform: translate(0, -8px) rotate(45deg);
    }

    #burger-popup {
        overflow: hidden;
        position: absolute;
        background-color: white;
        top: 8vh;
        margin: 0;
        right: 10%;
        /* height: auto; */
        width: 0;
        opacity: 0;
        box-shadow: rgba(0, 0, 0, 0.25) 0px 54px 55px, rgba(0, 0, 0, 0.12) 0px -12px 30px, rgba(0, 0, 0, 0.12) 0px 4px 6px, rgba(0, 0, 0, 0.17) 0px 12px 13px, rgba(0, 0, 0, 0.09) 0px -3px 5px;
        border-radius: 2%;
        text-align: center;
    }

    #popup-list {
        list-style-type: none;
        text-align: left;
    }

    .bp-item {
        display: block;
        justify-content: center;
        text-align: center;
        display: block;
    }

    .bp-item a {
        display: block;
        left: 0;
        right: 50%;
        margin-top: 20px;
        margin-right: 100vw;
        padding: 0;
        font-size: auto;
        opacity: 0;
    }

</style>