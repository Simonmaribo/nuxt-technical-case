<template>
    <div>
        <button @click.prevent="previous" :disabled="reachedScrollLimit == 1">Forrige</button>
        <button @click.prevent="next" :disabled="reachedScrollLimit == 2">Næste</button>

        <div class="slider" ref="slider" 
            @mousedown="start" 
            @mouseenter="stop" 
            @mousemove.prevent="scroll"
            @mouseleave="stop"
            @mouseup="stop"
            @scroll="checkIfReachedScrollLimit"
        >
            <slot/>
        </div>
    </div>
</template>

<script>
export default {
    name: 'DraggableContainer',
    data() {
        return {
            startX: 0, // X-position når drag startes
            scrollLeft: 0, // Hvor meget der er scrollet
            isPressed: false, // Om drag er startet eller ej (mousedown/mouseup)
            reachedScrollLimit: 1 // 0 = no limit, 1 = left limit, 2 = right limit
        }
    },
    methods: {
        start(e) {
            this.isPressed = true
            this.startX = e.pageX;
            this.scrollLeft = this.$refs.slider.scrollLeft;
            this.$refs.slider.style.cursor = 'grabbing';
        },
        stop(e) {
            this.isPressed = false;
            this.$refs.slider.style.cursor = 'grab';
        },

        scroll(e) {
            if(this.isPressed){
                // Scroll containeren med den afstand som den har haft siden scroll-start.
                this.scrollTo(this.scrollLeft - (e.pageX - this.startX), 'instant')
            }
        },
        next() {
            this.scrollTo(this.$refs.slider.scrollLeft + 420, 'smooth');
        },
        previous() {
            this.scrollTo(this.$refs.slider.scrollLeft - 420, 'smooth');
        },
        scrollTo(x, behavior) {
            this.$refs.slider.scrollTo({
                left: x,
                behavior: behavior || 'instant'
            });
            this.checkIfReachedScrollLimit();
        },
        checkIfReachedScrollLimit() {

            // Hvis der ikke er blevet scrollet (dragget)
            if(this.$refs.slider.scrollLeft == 0) 
                this.reachedScrollLimit = 1;

            // Scroll Width = bredden af  scroll-containeren med overflow
            // Scroll Left = hvor meget der er scrollet
            // Client width = bredden af scroll-containeren uden overflow
            // hvis scrollleft + clientwidth er lig med scrollwidth, så er der ikke mere at scrolle til højre
            else if(this.$refs.slider.scrollLeft + this.$refs.slider.clientWidth >= this.$refs.slider.scrollWidth) 
                this.reachedScrollLimit = 2;

            else this.reachedScrollLimit = 0;
        }
    }
}
</script>


<style scoped>
.slider {
    overflow: hidden; /* scroll: to show scroll bars */
    display: flex;
    gap: 30px;
    cursor: grab;
}
</style>