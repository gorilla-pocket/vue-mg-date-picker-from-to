<template>
<div class="d-flex">
    <div class="align-self-center mr-2" v-if="label">
        {{label}}
    </div>
    <div class="">
        <date-picker-normal v-model="from" />
    </div>
    <div class="align-self-center mx-2">
        ～
    </div>
    <div class="mr-0">
        <date-picker-normal v-model="to" />
    </div>
</div>
</template>

<script>
import moment from 'moment';
import DatePickerNormal from 'vue-mg-date-picker-normal'
export default {
    props: [
        'label',
        'from_dt',
        'to_dt'
    ],
    data () {
        return {
            from: '',
            to: '',
        }
    },
    mounted: function () {
        if (moment(this.from_dt).isValid()) {
            this.from = this.from_dt
        } else {
            this.from = ''
        }
        if (moment(this.to_dt).isValid()) {
            this.to = this.to_dt
        } else {
            this.to = ''
        }
    },
    watch: {
        from_dt: function () {
            if (moment(this.from_dt).isValid()) {
                this.from = this.from_dt
            } else {
                this.from = ''
                this.$emit('update:from_dt', '')
            }
        },
        to_dt: function () {
            if (moment(this.to_dt).isValid()) {
                this.to = this.to_dt
            } else {
                this.to = ''
                this.$emit('update:to_dt', '')
            }
        },
        from: function (val) {
            this.$emit('update:from_dt', val)
        },
        to: function (val) {
            this.$emit('update:to_dt', val)
        },
    },
    methods: {
        //
    },
    components: {
        DatePickerNormal,
    }
}
</script>

<style lang="scss" scoped>
</style>
