<template>
  <div class="about">
    <div class="about__hero">
      <div class="about__image">
        <img
          :src="require(`~/assets/images/about/${fields.top.image}`)"
          alt=""
        />
        <p class="about__text text">{{ fields.top.imageDescr }}</p>
      </div>
      <h4 class="about__subtitle subtitle">{{ fields.top.subtitle }}</h4>
      <h2 class="about__title title">{{ fields.top.title }}</h2>
      <p class="about__text text">{{ fields.top.descr }}</p>
    </div>
    <div class="about__team">
      <h4 class="about__subtitle subtitle">
        {{ fields.aboutTeams.subtitle }}
      </h4>
      <h2 class="about__title title">{{ fields.aboutTeams.title }}</h2>
      <div class="about__teams">
        <div
          class="about__team"
          v-for="team in fields.aboutTeams.teams"
          :key="team.id"
        >
          <div class="about__team-img">
            <img :src="require(`~/assets/images/about/${team.photo}`)" alt="" />
          </div>
          <div class="about__team-name name">{{ team.name }}</div>
          <div class="about__team-position position">{{ team.position }}</div>
          <div class="about__team-socials socials">
            <Social
              :socialIcon="social.name"
              :socialLink="social.link"
              orange
              v-for="social in team.socials"
              :key="social.id"
            />
          </div>
        </div>
      </div>
    </div>
    <div class="about__stats">
      <div
        class="about__counter counter"
        v-for="counter in fields.aboutStats"
        :key="counter.id"
      >
        <p class="counter__number">{{ counter.number }}</p>
        <p class="counter__text subtitle-grey">{{ counter.text }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import Social from "~/components/Social";
export default {
  name: "componentAbout",
  props: {
    fields: Object,
  },
  components: {
    Social,
  },
};
</script>

<style>
</style>
