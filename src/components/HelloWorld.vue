<template>
  <v-container class="fill-height" fluid>
    <v-col cols="12">
      <v-responsive
        class="align-centerfill-height mx-auto "

      >

        <div class="text-left">
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
              <v-card-text class=" ">
                <p class="pa-1 text-body-1 text-medium-emphasis">I am a passionate coder and web developer who thrives
                  in
                  fullstack positions,
                  as they allow me to take on diverse roles.</p>
                <p class="pa-1 text-body-1 text-medium-emphasis">Whether it is creating consumer-facing interfaces with
                  Vue.js
                  and Material Design (Vuetify)</p>
                <p class="pa-1 text-body-1 text-medium-emphasis">Or developing business-facing backends using frameworks
                  ranging
                  from Node.js with Express or Nest.js to PHP with Laravel.I have experience in API integrations
                  and application infrastructure through Linux bash/zsh scripting and DevOps pipelines.</p>
              </v-card-text>
              <v-card-actions class="ml-2">
                <v-btn color="primary" variant="outlined" @click="scrollToElement('xp')">Experience</v-btn>
                <v-btn color="secondary" variant="outlined" @click="scrollToElement('edu')">Education</v-btn>
              </v-card-actions>

              <v-card-title>
                <h2 class="text-h5 font-weight-bold "><span>About me</span></h2>
              </v-card-title>
              <v-card-text class="">
                <p class="pa-1  text-medium-emphasis font-weight-medium">My personal interests include home automation,
                  3D
                  printing, and electronics,
                  which keep me continuously learning and experimenting. I have a deep love for
                  entrepreneurship and am always on the lookout for new business ideas and unmet market needs.</p>
                <p class="pa-1  text-medium-emphasis font-weight-medium"> I am
                  looking to join a team that shares my mentality and values out-of-the-box thinking, fostering
                  collaboration and mutual growth through knowledge exchange.</p>

                <p class="pa-1 mt-2 font-weight-regular text-high-emphasis">Does the above sounds like someone you would
                  like to meet && possibly
                  collaborate with?</p>
              </v-card-text>
              <v-card-actions v-if="queryParams.email" class="ml-2">

                <v-btn :href="mailto" color="secondary" variant="outlined">Yes let's have a call
                </v-btn>
              </v-card-actions>
              <v-card-text class=" text-mono">


                <p class="pa-1 mt-2 text-body-1 text-medium-emphasis">* If my profile does not match your current
                  business
                  needs,
                  thank you for taking the time to read this.<br> An email to let me know would be greatly appreciated.
                </p>
                <p class="pa-1 mt-2 text-body-1 ">Thanks in advance 😊</p>


                <p></p>
              </v-card-text>
            </v-card>
          </v-col>
          <v-col cols="12"
          >
            <v-responsive>
              <v-tabs
                v-model="active" center-active
              >
                <v-tab :variant="variants.xp" class="mr-1" value="xp">Experience</v-tab>
                <v-tab :variant="variants.edu" value="edu">Education</v-tab>
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
                      dot-color="blue-grey"

                    >
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
            </v-responsive>


          </v-col>


        </v-row>
      </v-responsive>
    </v-col>
  </v-container>
</template>

<script>

export default {
  data() {
    const xp = [
      {
        company: "siteland.gr",
        position: "intern Junior Developer",
        stack: ["PHP", "Magento2", "Jquery", "Bootstrap"],
        description: "Redesign of company site, creation of landing pages, newsletters, storefronts (phtml/xml) for our Magento 2 Clients. Hardware and software implementation of Express.js server for RFID entrance control.",
        period: "2019"
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
        description: "<p>Responsible for product development,delivery, maintenance of internal tools.<p class='my-1'>  Carbonplan a multi-database multi-tenant tool for calculating the Carbon footprint of companies.<p class='my-1'> Wasteplan a waste channel management software used by the private and public sector to operate and reporting environmental processes</p>",
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
        period: "2017-2018"
      },
      {
        organisation: "Fonty's",
        location: "Eindhoven, Netherlands",
        course: "Undergraduate Bsc ICT , Software engineering",
        description: "Courses: HTML,CSS,JS,C sharp",
        period: "2017-2018"
      },
      {
        organisation: "Deree",
        location: "Ag.Paraskeui, Greece",
        course: "Undergraduate Bsc CS  Software engineering",
        description: "Courses: Java,C++,Python, Project Management",
        period: "2017-2018"
      }
    ]

    const variant_map = {
      "active": "tonal",
      "inactive": "flat"
    }

    return {

      xp, edu, active: "xp",
      variant_map,

      variants: {
        "xp": variant_map.active,
        "edu": variant_map.inactive
      }
    }
  },
  computed: {
    queryParams() {
      return Object.fromEntries(new URLSearchParams(new URL(window.location).search).entries());
    },
    mailto() {
      let subject = "Let's have a call"
      let body = `Hey Jason, <br>  I saw your cv from ${window.location.host} and I would like to connect`
      return `mailto:${this.queryParams.email}?subject=${subject}&body=${body}`
    },
    timeline() {

      if (this.$vuetify.display.smAndDown) {
        window.alert(1)
        return "end"
      } else {

      }
      return undefined

    },


  },
  methods: {

    scrollToElement(id) {
      // Find the element by its ID
      this.active = id
      const element = document.getElementById(id);
      if (element) {

        // Scroll to the element
        element.scrollIntoView({behavior: 'smooth'});
      }

    }
  }
}
</script>
<style scoped>
.v-timeline .v-timeline-item .v-card {
  max-width: 800px !important;


}

</style>
