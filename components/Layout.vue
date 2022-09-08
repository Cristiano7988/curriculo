<template>
    <main :style="[BG.grey, color.black]">
        <Header />
        <div class="flex-container">
            <div class="experiences">
              <div class="flex-container padding-vertical padding-horizontal">
                <!-- <h2 style>Experiências</h2> -->
                <h2 style>Experiences</h2>
              </div>
              <div class="experience" v-for="( {start, end, role, company, details, projects, stack, address, status}, index) in experiences" :key="index">
                    <div class="company padding-horizontal">
                        <div class="flex-container">
                            <BarItem
                                :topText="company"
                                :bottomText="address"
                            />
                            <BarItem
                                class="italic"
                                :topText="role"
                                :bottomText="start + ' - ' + end"
                                :pillText="status"
                            />
                        </div>
                    </div>
                    <div v-if="!index" class="titles flex-container padding-horizontal">
                        <Title
                            v-for="({englishTitle, column}, key) in titles"
                            :key="key"
                            :style="color.green"
                            :title="englishTitle"
                            :class="[column]"
                        />
                    </div>
                    <div class="flex-container details padding-horizontal padding-vertical">
                        <div class="large column">
                            <p :style="[color.black]" v-for="(detail, key) in details" :key="key">{{detail}}</p>
                        </div>
                        <div v-if="projects" class="medium column">
                            <ul>
                                <li :style="BG.green" v-for="({link}, key) in projects" :key="key">
                                    <a :style="color.grey" :href="'https://'+link">{{link}}</a>
                                </li>
                            </ul>
                        </div>
                        <div v-if="stack" class="small column">
                            <ul>
                                <li :style="BG.blue" v-for="(tool, key) in stack" :key="key">
                                    <span :style="color.grey">{{tool}}</span>
                                </li>
                            </ul>
                        </div>
                    </div>
              </div>
            </div>
        </div>
    </main>
</template>

<script>
// import experiences from "@/assets/data/experiences.json";
import experiencesEnglish from "@/assets/data/experiences-english.json";
import { color, BG } from "@/assets/styles/paleta.json";

export default {
    data() {
        return {
            // experiences,
            experiences: experiencesEnglish,
            color,
            BG,
            titles: [
                {
                    title: "Detalhes",
                    englishTitle: "Details"
                },
                {
                    title: "Projetos",
                    englishTitle: "Projects",
                    column: "medium"
                },
                {
                    title: "Stack",
                    englishTitle: "Stack",
                    column: "small"
                }
            ],
        };
    }
}
</script>

<style>
    main {
        padding: 0;
        margin: 0;
    }

    /* Análogo - Color Wheel */
    .experience:nth-child(even) {
        background: #F0E4D1;
    }

    .company {
        border-top: solid;
        border-bottom: solid;
        border-width: 1px;
    }

    .flex-container {
        display: flex;
        justify-content: space-between;
    }

    .titles {
        padding-top: 40px;
    }

    .italic b {
        font-style: italic;
    }

    .pill {
        padding: 5px;
        margin: 5px;
        border-radius: 5px;
        font-size: 10px;
        letter-spacing: 1px;
    }

</style>