<template>
  <div class="home">
    <TopNavBar />
    <Timer />
    <InfoCards />
  </div>
</template>

<script>
import TopNavBar from '@/components/NavBar/Top'
import InfoCards from '@/components/InfoCards'
import Timer from '@/components/Timer'

import displayTime from '@/utils/displayTime'

export default {
  components: {
    TopNavBar,
    InfoCards,
    Timer,
  },

  beforeMount() {
    this.$store.commit('timer/init')
  },

  head() {
    return {
      title: displayTime(this.$store.state.timeLeft),
    }
  },
}
</script>
