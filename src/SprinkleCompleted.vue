<template>  
    <div id = "center">
        <div id = "circle" 
        :style="{ 'background-color': backgroundColor,
                  'border': borderType}">
            <div id = "text" 
            :style="{'color': textColor}">
                {{text}}
            </div>
        </div>
    </div>
</template>
<script>
    import anime from 'animejs'
    export default {
        name: "VueSprinkleCompleted",
        props: {
			text: {
				type: String,
				default: 'Complete!'
			},
			backgroundColor: {
				type: String,
				default: ' #8b6dfa'
            },
            borderType: {
				type: String,
				default: '2px dashed #8b6dfa'
            },
            textColor: {
				type: String,
				default: 'white'
			},
		},
        data(){
            return{
                flag: false,
            }
        },
        watch: {
            flag(){
            var textWrapper = document.querySelector('#text');
            textWrapper.innerHTML = textWrapper.textContent.replace(/\S/g, "<span class='letter'>$&</span>");

            anime.timeline()
            .add({
                targets: '#circle',
                rotate: {
                    value: 360,
                    duration: 1800,
                    easing: 'easeInOutSine'
                },
                scale: {
                    value: 4,
                    duration: 1600,
                    delay: 800,
                    easing: 'easeInOutQuart'
                },
                delay: 250
            })
            .add({
                    targets: '#text .letter',
                    scale: [4,1],
                    opacity: [0,1],
                    translateZ: 0,
                    easing: "easeOutExpo",
                    duration: 950,
                    delay: (el, i) => 70*i,
            })
            .add({
                    targets: '#circle',
                    scale: [4,1],
                    easing: "easeOutSine",
                    complete: function(anim) {
                         var elmnt = document.getElementById("circle");
                         elmnt.remove();
                    }
            });
        
            },
        },
        mounted() {
            this.flag = true
        },
    }
</script>
<style scoped>
   #circle{
        margin:10px auto;
        border-radius: 3em;
        width: 10em;
        height: 2.5em;
   }
#text{
        text-align: center;
        line-height:40px;
        padding:0 20px;
        font-size: 150%;
        font-stretch: extra-expanded;
        font-family: cursive;
}
 #center {
  position: absolute;
  left: 50%;
  right: 50%;
  margin: auto;
  top: 0;
  bottom: 0;
  height: 1em;
}
</style>