<template>
    <div>
        <span ref="numberGrow" :data-time="time" class="number-grow" :data-value="value">0</span>
    </div>
</template>

<script>
    export default {
        name: "cont-to",
        props: {
            value: {
                type: Number,
                default() {
                    return 123
                }
            },
            time: {
                type: Number,
                default() {
                    return 600
                }
            },
        },

        methods: {
            numberGrow (ele) {
                let _this = this

                let step = (_this.value * 10) / (_this.time * 1000)
                let current = 0
                let start = 0
                let t = setInterval(function () {
                    start += step
                    if (start > _this.value) {
                        clearInterval(t)
                        start = _this.value
                        t = null
                    }
                    if (current === start) {
                        return
                    }
                    current = start
                    ele.innerHTML = current.toFixed(0)
                }, 1)
            }
        },
        mounted() {
            this.numberGrow(this.$refs.numberGrow)
        },
    }
</script>

<style scoped>

</style>
