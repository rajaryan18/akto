<template>
    <div>
        <div class="layout-border pl-8" style="padding-bottom: 12px">
            <div v-if="title" class="pt-6">
                <div>
                    <span class="board-name">{{ title || 'Loading...' }}</span>
                </div>
                <div v-if="description">
                    <span class="board-description">{{description}}</span>
                </div>
            </div>
            <div v-else>
                <slot name="title"/>
            </div>
        </div>
        <div>
            <slot/>
        </div>
    </div>
</template>

<script>
    import obj from "@/util/obj";

    export default {
        name: "SimpleLayout",
        props: {
            title: obj.strN,
            description: obj.strN
        }
    }

</script>

<style scoped lang="sass">
.board-name
    font-weight: 600
    font-size: 24px
    color: var(--themeColorDark)

.board-description
    font-weight: 500
    font-size: 13px
    color: var(--themeColorDark)
    opacity: 0.7
    padding-top: 4px
.layout-border
    border-bottom: 1px solid var(--themeColorDark16)
</style>