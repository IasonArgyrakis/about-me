<template>
  <v-container class="fill-height" fluid>
    <v-col cols="12">
      <v-responsive
        class="align-centerfill-height mx-auto "

      >

        <div class="text-left">
          <h1 class="text-h2 font-weight-bold ">Iason Argyrakis</h1>
          <h2 class="text-h3 font-weight-medium">FullStack Developer</h2>
          <h4 class="text-disabled text-h4 text-high-emphasis opacity-50 font-weight-regular">
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
                <v-btn color="primary" @click="scrollToElement('xp')" variant="outlined">Experience</v-btn>
                <v-btn color="secondary" @click="scrollToElement('edu')" variant="outlined">Education</v-btn>
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
              <v-card-actions class="ml-2">
                <v-btn color="secondary" variant="outlined">Yes let's have a call</v-btn>
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


          <!--          <v-col cols="12"-->
          <!--                 md="6">-->
          <!--            <v-timeline side="end">-->
          <!--              <v-timeline-item-->
          <!--                v-for="(item,index) in edu"-->
          <!--                :key="index"-->
          <!--                size="small"-->
          <!--              >-->
          <!--                <pre>{{item}}</pre>-->
          <!--              </v-timeline-item>-->
          <!--            </v-timeline>-->
          <!--          </v-col>-->
          <v-col cols="12"
          >
            <v-responsive>
              <v-timeline
                id="xp"
              :side="timeline">
                <v-timeline-item
                  v-for="(item,index) in xp"
                  dot-color="blue-grey"
                >
                  <v-card>
                    <v-card-title v-if="item.company">
                      <span class="text-overline">{{ item.company }} - {{ item.period }}</span>
                    </v-card-title>
                    <v-card-subtitle v-if="item.position">
                      <p class="text-overline">{{ item.position }}</p>
                    </v-card-subtitle>
                    <v-card-text v-if="item.description" v-html="item.description">
                    </v-card-text>
                    <v-card-text v-if="item.stack">
                    <span v-for="(stack,index) in item.stack">
                   <v-chip class="ml-1">{{ stack }}</v-chip>
                </span>
                    </v-card-text>
                  </v-card>


                </v-timeline-item>
              </v-timeline>
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
        organisation: "E",
        location: "loc",
        course: "Intern Dev",
        description: "description",
        period: "description"
      }
    ]
    return {
      xp, edu
    }
  },
  computed: {
    timeline() {
      if (this.$vuetify.display.smAndDown){
        return "end"
      }
      return undefined

    }

  },
  methods: {
    scrollToElement(id) {
      // Find the element by its ID
      const element = document.getElementById(id);
      if (element) {
        // Scroll to the element
        element.scrollIntoView({ behavior: 'smooth' });
      }
    }
  }
}
</script>
