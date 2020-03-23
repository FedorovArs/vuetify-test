<template>
    <div>
        <v-navigation-drawer absolute temporary v-model="drawer" app :width="400">
            <v-list nav dense>

                <v-list-item-group active-class="light-blue--text text--accent-4">
                    <!--                    <v-list-group active-class="light-blue&#45;&#45;text text&#45;&#45;accent-4" @click='goTheory'>-->


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
                                    <v-list-item-title class="ml-6">Административное деление</v-list-item-title>
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
                                    <router-link to="/theory/algorithms" class="link">Синхронизация с ГИС ПА
                                    </router-link>
                                </v-list-item-title>
                            </v-list-item>

                            <v-list-item>
                                <v-list-item-icon>
                                    <v-icon>mdi-folder-multiple</v-icon>
                                </v-list-item-icon>
                                <v-list-item-title>
                                    <router-link to="/theory/algorithms" class="link">Переопределение ОПС</router-link>
                                </v-list-item-title>
                            </v-list-item>

                            <v-list-item>
                                <v-list-item-icon>
                                    <v-icon>mdi-folder-multiple</v-icon>
                                </v-list-item-icon>
                                <v-list-item-title>
                                    <router-link to="/theory/algorithms" class="link">Труднодоступные ОПС</router-link>
                                </v-list-item-title>
                            </v-list-item>
                        </v-list-group>

                        <v-list-group sub-group no-action="true">
                            <template v-slot:activator>
                                <v-list-item-icon>
                                    <v-icon>mdi-folder-multiple</v-icon>
                                </v-list-item-icon>
                                <v-list-item-content>
                                    <v-list-item-title>СтрокиОтКуда</v-list-item-title>
                                </v-list-item-content>
                            </template>

                            <!--                            <v-list-item>-->
                            <!--                                <v-list-item-title>-->
                            <!--                                    <router-link to="/theory/algorithms" class="link">Алгоритмы решения задач</router-link>-->
                            <!--                                </v-list-item-title>-->
                            <!--                            </v-list-item>-->
                        </v-list-group>

                        <v-list-group sub-group>
                            <template v-slot:activator>
                                <v-list-item-icon>
                                    <v-icon>mdi-folder-multiple</v-icon>
                                </v-list-item-icon>
                                <v-list-item-content>
                                    <v-list-item-title>СтрокиПоНП</v-list-item-title>
                                </v-list-item-content>
                            </template>

                            <!--                            <v-list-item>-->
                            <!--                                <v-list-item-title>-->
                            <!--                                    <router-link to="/theory/algorithms" class="link">Алгоритмы решения задач</router-link>-->
                            <!--                                </v-list-item-title>-->
                            <!--                            </v-list-item>-->
                        </v-list-group>

                        <v-list-group sub-group>
                            <template v-slot:activator>
                                <v-list-item-icon>
                                    <v-icon>mdi-folder-multiple</v-icon>
                                </v-list-item-icon>
                                <v-list-item-content>
                                    <v-list-item-title>Cut Off</v-list-item-title>
                                </v-list-item-content>
                            </template>

                            <!--                            <v-list-item>-->
                            <!--                                <v-list-item-title>-->
                            <!--                                    <router-link to="/theory/algorithms" class="link">Алгоритмы решения задач</router-link>-->
                            <!--                                </v-list-item-title>-->
                            <!--                            </v-list-item>-->
                        </v-list-group>

                        <v-list-group sub-group>
                            <template v-slot:activator>
                                <v-list-item-icon>
                                    <v-icon>mdi-folder-multiple</v-icon>
                                </v-list-item-icon>
                                <v-list-item-content>
                                    <v-list-item-title>Варианты расчета (сводная)</v-list-item-title>
                                </v-list-item-content>
                            </template>

                            <!--                            <v-list-item>-->
                            <!--                                <v-list-item-title>-->
                            <!--                                    <router-link to="/theory/algorithms" class="link">Алгоритмы решения задач</router-link>-->
                            <!--                                </v-list-item-title>-->
                            <!--                            </v-list-item>-->
                        </v-list-group>

                    </v-list-group>

                    <v-list-group
                            active-class="light-blue--text text--accent-4"
                            @click='goPractice'
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
                                <router-link to="/practice/formulatrainer" class="link">Тренировка формул</router-link>
                            </v-list-item-title>
                        </v-list-item>

                        <v-list-item>
                            <v-list-item-title>
                                <router-link to="/practice/tasktrainer" class="link">Тренажер решения задач
                                </router-link>
                            </v-list-item-title>
                        </v-list-item>

                        <v-list-item>
                            <v-list-item-title>
                                <router-link to="/practice/tasks" class="link">Задачи</router-link>
                            </v-list-item-title>
                        </v-list-item>

                    </v-list-group>
                </v-list-item-group>

                <!--        <v-list-item link>-->
                <!--          <v-list-item-action>-->
                <!--            <v-icon>mdi-folder-multiple</v-icon>-->
                <!--          </v-list-item-action>-->
                <!--          <v-list-item-content>-->
                <!--            <v-list-item-title>Внутренние отправления</v-list-item-title>-->
                <!--          </v-list-item-content>-->
                <!--        </v-list-item>-->

                <!--        <v-list-item link>-->
                <!--          <v-list-item-action>-->
                <!--            <v-icon>mdi-folder-multiple</v-icon>-->
                <!--          </v-list-item-action>-->
                <!--          <v-list-item-content>-->
                <!--            <v-list-item-title>Международные отправления</v-list-item-title>-->
                <!--          </v-list-item-content>-->
                <!--        </v-list-item>-->

            </v-list>
        </v-navigation-drawer>

        <v-toolbar dark class="primary">
            <v-app-bar-nav-icon @click.stop="drawer = !drawer"/>
            <v-toolbar-title v-text="projectTitle"></v-toolbar-title>
        </v-toolbar>
    </div>
</template>

<script>
    export default {
        data: () => ({
            projectTitle: "Управление контрольными сроками",
            drawer: false
        })
    };
</script>

<style scoped></style>
