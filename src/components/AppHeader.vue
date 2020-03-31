<template>
    <div>
        <v-navigation-drawer absolute temporary v-model="drawer" app :width="400">
            <v-img class="mt-4 mb-4" src="@/assets/russian_post.png" contain height="20vh"></v-img>
            <v-divider></v-divider>

            <v-list nav dense>
                <v-list-item-group active-class="light-blue--text text--accent-4">
                    <v-list-group>
                        <template v-slot:activator>
                            <v-list-item-icon>
                                <v-icon>mdi-folder-multiple</v-icon>
                            </v-list-item-icon>
                            <v-list-item-content>
                                <v-list-item-title>Внутренние отправления</v-list-item-title>
                            </v-list-item-content>
                        </template>

                        <v-list-group sub-group>
                            <template v-slot:activator>
                                <v-list-item-icon>
                                    <v-icon>mdi-folder-multiple</v-icon>
                                </v-list-item-icon>
                                <v-list-item-content>
                                    <v-list-item-title :class="ml_5">Административное деление</v-list-item-title>
                                </v-list-item-content>
                            </template>

                            <v-list-item>
                                <v-list-item-icon>
                                    <v-icon>mdi-folder-multiple</v-icon>
                                </v-list-item-icon>
                                <v-list-item-title>
                                    <router-link to="/" class="link">Тип НП</router-link>
                                </v-list-item-title>
                            </v-list-item>

                            <v-list-item>
                                <v-list-item-icon>
                                    <v-icon>mdi-folder-multiple</v-icon>
                                </v-list-item-icon>
                                <v-list-item-title>
                                    <router-link to="/about" class="link">Синхронизация с ГИС ПА</router-link>
                                </v-list-item-title>
                            </v-list-item>

                            <v-list-item>
                                <v-list-item-icon>
                                    <v-icon>mdi-folder-multiple</v-icon>
                                </v-list-item-icon>
                                <v-list-item-title>
                                    <router-link
                                        to="/theory/algorithms"
                                        class="link"
                                    >Переопределение ОПС</router-link>
                                </v-list-item-title>
                            </v-list-item>

                            <v-list-item>
                                <v-list-item-icon>
                                    <v-icon>mdi-folder-multiple</v-icon>
                                </v-list-item-icon>
                                <v-list-item-title>
                                    <router-link
                                        to="/theory/algorithms"
                                        class="link"
                                    >Труднодоступные ОПС</router-link>
                                </v-list-item-title>
                            </v-list-item>
                        </v-list-group>

                        <v-list-group sub-group no-action="true">
                            <template v-slot:activator>
                                <v-list-item-icon>
                                    <v-icon>mdi-folder-multiple</v-icon>
                                </v-list-item-icon>
                                <v-list-item-content>
                                    <v-list-item-title :class="ml_5">СтрокиОтКуда</v-list-item-title>
                                </v-list-item-content>
                            </template>
                        </v-list-group>

                        <v-list-group sub-group>
                            <template v-slot:activator>
                                <v-list-item-icon>
                                    <v-icon>mdi-folder-multiple</v-icon>
                                </v-list-item-icon>
                                <v-list-item-content>
                                    <v-list-item-title :class="ml_5">СтрокиПоНП</v-list-item-title>
                                </v-list-item-content>
                            </template>
                        </v-list-group>

                        <v-list-group sub-group>
                            <template v-slot:activator>
                                <v-list-item-icon>
                                    <v-icon>mdi-folder-multiple</v-icon>
                                </v-list-item-icon>
                                <v-list-item-content>
                                    <v-list-item-title :class="ml_5">Cut Off</v-list-item-title>
                                </v-list-item-content>
                            </template>
                        </v-list-group>

                        <v-list-group sub-group>
                            <template v-slot:activator>
                                <v-list-item-icon>
                                    <v-icon>mdi-folder-multiple</v-icon>
                                </v-list-item-icon>
                                <v-list-item-content>
                                    <v-list-item-title :class="ml_5">Варианты расчета (сводная)</v-list-item-title>
                                </v-list-item-content>
                            </template>
                        </v-list-group>
                    </v-list-group>

                    <v-list-group
                        active-class="light-blue--text text--accent-4"
                        @click="goPractice"
                    >
                        <template v-slot:activator>
                            <v-list-item-icon color="light-blue lighten-4">
                                <v-icon>mdi-folder-multiple</v-icon>
                            </v-list-item-icon>
                            <v-list-item-content>
                                <v-list-item-title>Международные отправления</v-list-item-title>
                            </v-list-item-content>
                        </template>

                        <v-list-item>
                            <v-list-item-title>
                                <router-link
                                    to="/practice/formulatrainer"
                                    class="link"
                                >Тренировка формул</router-link>
                            </v-list-item-title>
                        </v-list-item>

                        <v-list-item>
                            <v-list-item-title>
                                <router-link
                                    to="/practice/tasktrainer"
                                    class="link"
                                >Тренажер решения задач</router-link>
                            </v-list-item-title>
                        </v-list-item>

                        <v-list-item>
                            <v-list-item-title>
                                <router-link to="/practice/tasks" class="link">Задачи</router-link>
                            </v-list-item-title>
                        </v-list-item>
                    </v-list-group>
                </v-list-item-group>
            </v-list>
        </v-navigation-drawer>

        <v-toolbar dark class="primary">
            <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
            <v-toolbar-title v-text="projectTitle"></v-toolbar-title>
        </v-toolbar>
    </div>
</template>

<script>
let treeMenu = [
    {
        title: "Внутренние отправления",
        children: [
            {
                title: "Административное деление",
                children: [
                    { title: "Тип НП", path: "/" },
                    { title: "Синхронизация с ГИС ПА", path: "/about" },
                    { title: "Переопределение ОПС", path: "/" },
                    { title: "Труднодоступные ОПС", path: "/" }
                ]
            },
            { title: "СрокиОтКуда" },
            { title: "СрокиПоНП" },
            { title: "Cut off" },
            { title: "Варианты расчёта (сводная)" }
        ]
    },
    { title: "Международные отправления" }
];
export default {
    data: () => ({
        projectTitle: "Управление контрольными сроками",
        drawer: false,
        ml_5: "ml-5",
        menu: treeMenu
    })
};
</script>

<style scoped>
.link {
    text-decoration: none;
}
</style>
