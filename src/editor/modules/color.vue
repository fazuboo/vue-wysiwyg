<template>
    <div
        class="editrColorsContainer"
    >
        <div
            class="editrColor"
            v-for="color in colors"
            @click="selectColor(color)"
            :style="{ background:color }"
        ></div>
    </div>
</template>

<script>

export default {
    title: "color",
    icon: '<svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" viewBox="0 0 48 48"><path d="M14 28c-3.31 0-6 2.69-6 6 0 2.62-2.31 4-4 4 1.84 2.44 4.99 4 8 4 4.42 0 8-3.58 8-8 0-3.31-2.69-6-6-6zM41.41 9.26l-2.67-2.67c-.78-.78-2.05-.78-2.83 0L18 24.5l5.5 5.5 17.91-17.91c.79-.79.79-2.05 0-2.83z"/></svg>',
    description: "Change text color",

    data () {
      return {
        colors: ["#000000",  "#ffffff", "#C00000", "#FFC000", "#002060", "#0070C0", "#5BB9FF",  "#D125C9" , "#949494", "#7030A0", "#71AF47" ]
      }
    },

    methods: {
      selectColor (color){
        this.$parent.closeDashboard();
        this.$emit("exec", "color", color);
        }
    }
};

</script>

<style>
    .editrColorsContainer{
        display: flex;
        align-items: center;
    }
    .editrColor{
        --d: 25px;
        width: var(--d);
        height: var(--d);
        margin-right: 2px;
        border-radius: 50%;
        cursor: pointer;
    }
</style>

