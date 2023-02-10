<template>
    <section>
        <div id="welcome-div">
            <span data-value="Hi, my name is">
                 Hi, my name is
            </span>  
            <span class="sp-name" data-value="Mateusz"> 
                 Mateusz 
             </span> 
             <br>
             <span class="sp-info" data-value="I'm a">
                 I'm a
             </span>
             <span class="sp-ment" data-value="computer science">
                 computer science
             </span>
             <span class="sp-info" data-value="student at"> 
                 student at
             </span>
             <span class="sp-ment" data-value="University of technology in Lodz">
                 University of technology in Lodz 
             </span>
        </div>
        <img src="../assets/pic.jpg" alt="pic" id="pic">
    </section>
</template>

<script>
export default {
    data() {
        return {
            upperCaseLetters: null,
            lowerCaseLetters: null
        }
    },
    methods: {
        randomizeText(curr) {
            let iteration = 0;
            const interval = setInterval(() => {
                curr.innerText = curr.innerText.split("").map((letter, index) =>  {
                if (index < iteration) {
                    return curr.dataset.value[index];
                }
                if (letter === " ") 
                    return " "
                if (letter.toLowerCase() === letter)
                    return this.lowerCaseLetters[Math.floor(Math.random() * 26)]
                else if (letter.toUpperCase() === letter) 
                    return this.upperCaseLetters[Math.floor(Math.random() * 26)]
            }).join("")

            if (iteration >= curr.dataset.value.length) clearInterval(interval)

            iteration += 1;
            }, 30);
        }
    },
    mounted() {
        let picture = document.getElementById("pic")
        let welcome = document.getElementById("welcome-div")
        let sec = document.querySelector("section")
        if (window.innerWidth < 440) {
            picture.style.width = "50vw"
            picture.style.height = "50vw"
            picture.style.marginTop = "0"
            welcome.style.width = "50vw"
        } else {
            sec.style.marginTop = "-150px"
        }
        
        this.upperCaseLetters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
        this.lowerCaseLetters = this.upperCaseLetters.toLowerCase();
        let spans = document.querySelectorAll("span")
        for (let i = 0; i < spans.length; i++) {
            this.randomizeText(spans[i]);
            spans[i].onmouseover = event => {
                this.randomizeText(event.target);
            }
        }
    }
}
</script>

<style>
    span {
        font-size: 50px;
        font-family: 'SF Mono', SFMono-Regular, ui-monospace,
        'DejaVu Sans Mono', Menlo, Consolas, monospace;
        font-weight: lighter;
    }

    .sp-name {
        font-weight: bold;
    }
    
    .sp-info {
        font-family: 'SF Mono', SFMono-Regular, ui-monospace, 'DejaVu Sans Mono', Menlo, Consolas, monospace;
        font-size: 20px;
    }

    .sp-ment {
        font-size: 20px;
    }

    section {
        overflow: hidden; 
    }

    #welcome-div {
        margin: -50px 0 50px 5px;
        float: left;
        width: 50vw;
    }
    
    #pic {
        margin-top: -100px;
        height: 20vw;
        width: 20vw;
        border-radius: 100%;
        box-shadow: rgba(0, 0, 0, 0.5) 0px 10px 36px 0px, rgba(0, 0, 0, 0.06) 0px 0px 0px 1px;
    }
</style>