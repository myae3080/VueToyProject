<template>
    <v-card>
        <!-- QUESTION : 2021-03-10  name of color is not working, but css color is ok...? -->
        <v-toolbar
            color="#26C6DA"
        >
            <v-app-bar-nav-icon></v-app-bar-nav-icon>

            <v-toolbar-title>Todo Sample</v-toolbar-title>

            <v-spacer></v-spacer>

            <v-btn icon>
                <v-icon>mdi-magnify</v-icon>
            </v-btn>

            <v-btn icon>
                <v-icon>mdi-dots-vertical</v-icon>
            </v-btn>

            <template v-slot:extension>
                <v-tabs
                    v-model="tab"
                    align-with-title
                >
                    <!-- QUESTION : 2021-03-04  색상 적용 안됨... -->
                    <v-tabs-slider color="red"></v-tabs-slider>

                    <v-tab
                        v-for="item in items"
                        :key="item"
                    >
                        {{ item }}
                    </v-tab>
                </v-tabs>
            </template>
        </v-toolbar>

        <v-tabs-items v-model="tab">
            <v-tab-item
                v-for="item in items"
                :key="item"
            >
                <v-card flat>
                    <v-card-text v-text="text"></v-card-text>
                </v-card>
            </v-tab-item>
        </v-tabs-items>
    </v-card>
</template>

<script>
export default {
    data() {
        return {
            tab: null,
            items: [
                'A', 'B', 'C'
            ],
            text: 'test'
        }
    }
}
</script>

<style scoped>

</style>