<template>
    <div class="wrap" ref="wrap">Hey! I am gonna become draggable and resizable.</div>
</template>

<script>
export default {
    name: 'DragResize',
    mounted() {
        this.observeEle()
    },
    methods: {
        observeEle()  {
            const resizeObj = new ResizeObserver(entries => {
                let rect = entries[0].contentRect
                console.log('element', entries[0].target)
                console.log('width', rect.width)
                console.log('height', rect.height)
            })

            resizeObj.observe(this.$refs.wrap)
        },
    },
}
</script>

<style scoped>
.wrap {
    background-color: rgb(112, 96, 255);
    color: #fff;
    border-radius: 10px;
    padding: 5px;
    width: 200px;
    cursor: pointer;
    user-select: none;
    resize: both;
    overflow: auto;
}
</style>