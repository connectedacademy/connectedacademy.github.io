<template lang="pug">
.page
  .container
    panel
      template(slot="title") Social Learning
      template(slot="body") Students publish notes to Twitter referencing segements of audio, thus sparking rich conversation and connected learning at a global scale.
      template(slot="content")
        .button.pink-button #[i.fas.fa-play] Watch Video
      template(slot="image")
        phone(:url="require('@/assets/images/shot-social.png')" position="bottom")

    panel
      template(slot="title") Media Focus
      template(slot="body") Attributed media associated with specific points in the conversation are at the heart of the conversation, encouraging meaningful interrogation and assesment.
      template(slot="detail")
      template(slot="image")
        .image(:style="{ 'background-image': `url(${require('@/assets/images/shot-media.png')})` }")

    panel(can-toggle)
      template(slot="title") Peer Feedback
      template(slot="body") Dynamically created chat groups allow for private peer feedback. Our algorithms group students based on a set of criteria to encourage self-assesment and critique.
      template(slot="image")
        phone(:url="require('@/assets/images/shot-dashboard.png')" position="top")
      template(slot="detail")
        h3 Group Allocation
        p Students are automatically added to groups of other students who have submitted work.
        h3 Feedback Visibilty
        p Students unlock feedback on their own work by providing feedback to others in their group. This method encourages participation and improves the quality and quantity of feedback between peers.

  .row.image(:style="{ 'background-image': `url(${require('@/assets/images/shot-classroom.jpg')})` }")
    h1 "Learning beyond the Classroom"

  .container

    panel(can-toggle)
      template(slot="title") Educator Insights
      template(slot="body") A suite of analytical tools enable educators to obtain new perspectives on student engagement and class progression. Offering the ability to increase engagement across the board.
      template(slot="image")
        phone(:url="require('@/assets/images/shot-dashboard.png')" position="bottom")
      template(slot="detail")
        h3 Student Engagement
        p Monitor how students are engaging with class content and issue prompts directly from the educator dashboard.

    panel
      template(slot="title") Explore the Demo
      template(slot="body") Try the interactive demo of Connected Academy to get a real feel for wether you could use it in your teaching space. Once you've had a play, reach out to us below!
      template(slot="content")
        a.button.pink-button(href="https://rocket.connectedacademy.io" target="_blank") #[i.fas.fa-rocket] Launch Demo

  .row.pink
    h3 An Open Lab project
    h5
      a(href="https://twitter.com/Jonathan_Worth") Jonathan Worth
      a(href="https://twitter.com/edjenkins91") Edward Jenkins
      a(href="https://twitter.com/tombartindale") Tom Bartindale

  .row.dark
    h3 Partners & Acknowledgements
    h5 Newcastle University | World Press Photo

  .row.terms
    h5 © 2018 Connected Academy, Open Lab, Newcastle University. All rights reserved.

</template>

<script>
import Panel from '@/components/Panel'
import Phone from '@/components/Phone'

export default {
  name: 'Home',
  components: {
    Panel,
    Phone
  },
  methods: {
    togglePanel (ref) {
      this.toggles[ref] = !this.toggles[ref]
    }
  }
}
</script>

<style lang="stylus" scoped>

@import '~stylus/shared'

</style>
