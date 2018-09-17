<template>
    <input type="text" :value="value">
</template>

<script>
    import Pikaday from 'pikaday'

    export default {
        props: {
            value: {
                type: String,
                required: true,
            },

            settings: {
                type: Object,
                default: () => ({}),
            },
        },

        data: () => ({
            pikaday: null,
        }),

        mounted() {
            this.pikaday = new Pikaday({
                ...this.defaultSettings,
                ...this.defaultEventSettings,
                ...this.settings,
            })
        },

        computed: {
            defaultSettings() {
                return {
                    field: this.$el,
                    format: 'YYYY-MM-DD',
                }
            },

            defaultEventSettings() {
                return {
                    onSelect: () => {
                        this.$emit('input', this.pikaday.toString())
                    },
                }
            },
        },
    }
</script>
