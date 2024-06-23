<template>
  <v-container class="fill-height">
    <v-col cols="12">
      <v-responsive
          class="align-centerfill-height mx-auto ">
        <div class="text-left pa-1">
          <h1 class="text-h1 font-weight-bold ">Hi 👋</h1>
          <h1 class="text-h2 font-weight-bold ">I'm Iason Argyrakis</h1>
          <h2 class="text-h3 font-weight-medium">FullStack Developer</h2>
          <h4 class="text-disabled text-h4 text-high-emphasis opacity-50 font-weight-regular"
              style="color: #08ff7ad6 !important;">
            ➜ Json git:(main) ✗</h4>
        </div>
        <div class="py-4"/>
        <v-row>
          <v-col cols="12">
            <v-card
                class="py-4"
                color="surface-variant"
                prepend-icon="mdi-laptop"
                rounded="lg"
                variant="tonal"
            >
              <v-card-title>
                <h2 class="text-h5 font-weight-bold "><span class="text-mono">Json</span> <span
                    class="text-disabled opacity-50 font-weight-regular">@Work</span></h2>
              </v-card-title>
              <v-card-text>
                <p class="pa-1 text-body-1 text-high-emphasis">
                  Hello! I'm a passionate coder and web developer, thriving in full-stack positions that let me embrace
                  diverse roles.
                </p>
                <p class="pa-1 text-body-1 text-high-emphasis">
                  <v-list>
                    <v-list-subheader>
                      I excel in:
                    </v-list-subheader>
                    <v-list-item>
                      <v-list-item-title>
                        Frontend Development:
                      </v-list-item-title>
                      <v-list-item-subtitle class="d-block">
                        <p>
                          Crafting engaging consumer-facing interfaces with Vue.js and Material Design (Vuetify).</p>
                      </v-list-item-subtitle>
                    </v-list-item>
                    <v-list-item>
                      <v-list-item-title>
                        Backend Development:
                      </v-list-item-title>
                      <v-list-item-subtitle class="d-block">
                        <p>
                          Building robust business-facing backends using frameworks like Node.js with Express or
                          Nest.js, and PHP with Laravel. </p>
                      </v-list-item-subtitle>
                    </v-list-item>
                    <v-list-item>
                      <v-list-item-title>
                        API Integrations & Infrastructure:
                      </v-list-item-title>
                      <v-list-item-subtitle class="d-block">
                        <p>
                          Enhancing applications through Linux bash/zsh scripting and DevOps pipelines.</p>
                      </v-list-item-subtitle>
                    </v-list-item>
                  </v-list>
                </p>
              </v-card-text>
              <v-card-title>
                <h2 class="text-h5 font-weight-bold ">About me</h2>
              </v-card-title>
              <v-card-text>
                <p class="pa-1 text-body-1 text-high-emphasis">
                  Beyond coding, I'm deeply invested in home automation, 3D printing, and electronics. These hobbies
                  keep me learning and experimenting. I also have a strong entrepreneurial spirit, constantly seeking
                  new business ideas and unmet market needs.
                </p>
              </v-card-text>
              <v-card-title>
                <h2 class="text-h5 font-weight-bold ">What I’m Looking For</h2>
              </v-card-title>
              <v-card-text>
                <p class="pa-1 text-body-1 text-high-emphasis">
                  I'm eager to join a team that values out-of-the-box thinking, collaboration, and mutual growth through
                  knowledge exchange. If my profile resonates with you, I’d love to connect and explore potential
                  collaboration.
                </p>
              </v-card-text>
              <v-card-text>
                <p class="pa-1 text-body-1 text-medium-emphasis">
                  If my skills and experience don't align with your current needs, thank you for considering my
                  application.</p>
                <v-card-actions class="ml-2">
                  <v-btn :href="mailJsonGood" color="primary" prepend-icon="mdi-email-check-outline" variant="elevated">
                    Let's have a call 🎉
                  </v-btn>
                  <v-btn :href="mailJsonBad" color="secondary" prepend-icon="mdi-email-remove-outline" variant="tonal">
                    Not a match 🙁
                  </v-btn>
                </v-card-actions>
                <p class="pa-1 text-body-1 text-medium-emphasis">
                  A quick email to let me know would be greatly appreciated.
                </p>
              </v-card-text>
            </v-card>
          </v-col>
          <v-col
              cols="12"

          >

              <v-tabs
                  v-model="active" center-active
              >
                <v-tab class="mr-1" value="xp">Experience</v-tab>
                <v-tab class="mr-1" value="skills">Skills</v-tab>
                <v-tab value="edu">Education</v-tab>
              </v-tabs>
            <v-tabs-window v-model="active">
                <v-tabs-window-item
                    value="xp"
                >
                  <v-timeline
                      id="xp"
                      side="end"
                  >
                    <v-timeline-item
                        v-for="(item,index) in xp"
                        dot-color="blue-grey">
                      <v-card class="text-wrap">
                        <v-card-title v-if="item.company">
                          <span class="text-overline text-wrap">{{ item.company }}</span>
                        </v-card-title>
                        <v-card-subtitle v-if="item.position" class="text-wrap">
                          <p class="text-overline">{{ item.position }}</p>
                          <p class="text-overline">{{ item.period }}</p>
                        </v-card-subtitle>
                        <v-card-text v-if="item.description" class="text-wrap" v-html="item.description">
                        </v-card-text>
                        <v-card-text v-if="item.stack" class="text-wrap">
                          <v-chip-group class="text-wrap" column>
                            <v-chip v-for="(stack,index) in item.stack">
                              {{ stack }}
                            </v-chip>
                          </v-chip-group>
                        </v-card-text>
                      </v-card>
                    </v-timeline-item>
                  </v-timeline>
                </v-tabs-window-item>
                <v-tabs-window-item
                    value="skills"
                >
                  <v-list ref="skills" class="pa-1">
                    <v-list-item v-for="(item, index) in skills" :key="index">
                      <v-row align="center">
                        <v-col cols="1">
                          <v-icon :icon="item.icon" color="white" size="40px"/>
                        </v-col>
                        <v-col>
                          <p class="text-body-1">{{ item.name }}</p>
                          <v-expand-x-transition>
                            <v-progress-linear v-show="this.targetIsVisible" v-model="item.confidence"
                                               :height="6"></v-progress-linear>
                          </v-expand-x-transition>

                        </v-col>
                      </v-row>


                    </v-list-item>
                  </v-list>
                </v-tabs-window-item>
              <v-tabs-window-item
                  value="edu">
                <v-timeline
                    id="edu"
                    side="start"
                >
                  <v-timeline-item
                      v-for="(item,index) in edu"
                      dot-color="blue-grey"
                  >
                    <v-card>
                      <v-card-title v-if="item.organisation" class="text-wrap">
                        <span class="text-overline">{{ item.organisation }}</span>
                      </v-card-title>
                      <v-card-subtitle v-if="item.course" class="text-wrap">
                        <p class="text-overline">
                          <v-icon>mdi-school-outline</v-icon>
                          {{ item.course }}
                        </p>
                      </v-card-subtitle>
                      <v-card-subtitle v-if="item.period" class="text-wrap">
                        <p class="text-overline">
                          {{ item.period }}
                        </p>
                      </v-card-subtitle>
                      <v-card-subtitle v-if="item.location" class="text-wrap">
                        <p class="text-overline">
                          <v-icon>mdi-map-marker-outline</v-icon>
                          {{ item.location }}
                        </p>
                      </v-card-subtitle>
                      <v-card-text v-if="item.description" class="text-wrap" v-html="item.description">
                      </v-card-text>
                      <v-card-text v-if="item.stack" class="text-wrap">
                          <span v-for="(stack,index) in item.stack">
                         <v-chip class="ml-1 mb-2">{{ stack }}</v-chip>
                      </span>
                      </v-card-text>
                    </v-card>
                  </v-timeline-item>
                </v-timeline>
              </v-tabs-window-item>
              </v-tabs-window>

          </v-col>
        </v-row>
      </v-responsive>
    </v-col>
  </v-container>
</template>
<script>

import {ref} from "vue";
import {useElementVisibility} from "@vueuse/core";
export default {
  setup() {
    const skills = ref(null)
    const targetIsVisible = useElementVisibility(skills)
    return {
      skills,
      targetIsVisible
    }
  },
  components: {
    useElementVisibility
  },
  data() {
    const xp = [
      {
        company: "siteland.gr",
        position: "intern Junior Developer",
        stack: ["PHP", "Magento2", "Jquery", "Bootstrap"],
        description: "Redesign of company site, creation of landing pages, newsletters, storefronts (phtml/xml) for our Magento 2 Clients. Hardware and software implementation of Express.js server for RFID entrance control.",
        period: "1/2019 - 12/2019"
      },
      {
        company: "DigitalUp.gr",
        position: "Junior FullStack",
        stack: ["PHP 7.4", "Magento2", "Jquery", "Bootstrap"],
        description: "Creation and Maintenance of high performing e-commerce platforms in collaboration with the Design department",
        period: "6/2021 – 11/2021"
      },
      {
        company: "Epignosis team:Talentcards.com",
        position: "FullStack Developer",
        stack: ["PHP 7.*", "PHP 8.*", "Laravel", "Vue2"],
        description: "Responsible for delivering new web features and maintaining existing ones (In-House Role)",
        period: "3/2022 - 12/2022"
      },
      {
        company: "Innoveco.gr",
        position: "FullStack Developer",
        stack: ["PHP 8.*", "Laravel 8", "Vue3"],
        description: "<p>Responsible for product development,delivery, maintenance of internal tools.<p class='my-1'>  Carbonplan a multi-database multi-tenant tool for calculating the Carbon footprint of companies.<p class='my-1'> Wasteplan a waste channel management software used by the private and public sector for environmental processes operations and reporting </p>",
        period: "3/2023 - 12/2023"
      },
      {
        company: "Valmore Technologies",
        position: "FullStack Developer",
        stack: [],
        description: "Individual contributor and external contractor for Neogen ",
        period: "1/2024 - 12/2024"
      },
      {
        company: "Neogen",
        position: "FullStack Developer - Individual contributor",
        stack: ["PHP", "nodejs", "express", "microservices", "mongodb"],
        description: "Individual contributor and external contractor for a saas product in  food safety management and operation",
        period: "1/2024 - 12/2024"
      },
    ]
    const edu = [
      {
        organisation: "Fonty's",
        location: "Eindhoven, Netherlands",
        course: "Undergraduate Bsc Mechanical Engineering",
        description: "Courses: Statics,Thermodynamics, 3D Design,C++",
        period: "2015 - 2017"
      },
      {
        organisation: "Fonty's",
        location: "Eindhoven, Netherlands",
        course: "Undergraduate Bsc ICT , Software engineering",
        description: "Courses: HTML,CSS,JS,C sharp",
        period: "2017 - 2018"
      },
      {
        organisation: "Deree",
        location: "Ag.Paraskeui, Greece",
        course: "Undergraduate Bsc CS  Software engineering",
        description: "Courses: Java,C++,Python, Project Management",
        period: "2019 - paused"
      }
    ]
    const skills = [

      {
        name: "Node",
        icon: "mdi-nodejs",
        confidence: "65"
      },
      {
        name: "Vue",
        icon: "mdi-vuejs",
        confidence: "75"
      },
      {
        name: "Vuetify",
        icon: "mdi-vuetify",
        confidence: "68"
      },
      {
        name: "PHP",
        icon: "mdi-language-php",
        confidence: "70"
      },
      {
        name: "Laravel",
        icon: "mdi-laravel",
        confidence: "70"
      },
      {
        name: "Docker",
        icon: "mdi-docker",
        confidence: "50"
      },

      {
        name: "Bash Scripting",
        icon: "mdi-bash",
        confidence: "40"
      },
      {
        name: "Git",
        icon: "mdi-source-repository",
        confidence: "70"
      },
      {
        name: "Html",
        icon: "mdi-language-html5",
        confidence: "70"
      },
    ]
    const email = "jasonargirakis@gmail.com"
    return {
      email,
      xp, edu, skills,
      active: "xp",
    }
  },
  computed: {
    mailJsonGood() {
      let subject = "Let's have a call | Iason Argyrakis | CV"
      let body = `Hey Jason,
       I saw your cv from ${window.location.host} and I would like to connect`
      return `mailto:${this.email}?subject=${subject}&body=${body}`
    },
    mailJsonBad() {
      let subject = "Not a match 🙁 | Iason Argyrakis | CV"
      let body = `Hey Jason,
       I saw your cv from ${window.location.host} and your profiles does not match our current business needs`
      return `mailto:${this.email}?subject=${subject}&body=${body}`
    },
  },
  methods: {
    circleStyle(item) {
      return {
        height: `${item.confidence}px`,
        width: `${item.confidence}px`,
        backgroundColor: '#bbb',
        borderRadius: '50%',
        display: 'inline-block'
      };
    },
    scrollToElement(id) {
      // Find the element by its ID
      this.active = id
      const element = document.getElementById(id);
      if (element) {        // Scroll to the element
        element.scrollIntoView({behavior: 'smooth'});
      }
    }
  },
  mounted() {
    this.xp.reverse()
    this.edu.reverse()
  }
}
</script>
<style scoped>
.v-timeline .v-timeline-item .v-card {
  max-width: 800px !important;
}


</style>
