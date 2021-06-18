<template>
  <div class="about">
    <div class="about__hero">
      <div class="about__image">
        <img :src="require(`~/assets/images/about/${fields.top.image}`)" alt="" />
        <div class="about__text text">{{ fields.top.imageDescr }}</div>
      </div>
      <div class="about__subtitle subtitle">{{fields.top.subtitle}}</div>
      <div class="about__title title">{{fields.top.title}}</div>
      <div class="about__text text">{{fields.top.descr}}</div>
    </div>
    <div class="about__team">
      <div class="about__subtitle subtitle">our experts</div>
      <div class="about__title title">Meet the team</div>
      <div class="about__teams">
        <div class="about__team" v-for="team in fields.aboutTeams.teams" :key="team.id">
          <div class="about__team-img">
            <img src="#" alt="" />
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
      <div class="about__counter counter">
        <span class="counter__number">990</span>
        <span class="counter__text">happy customers</span>
      </div>
      <div class="about__counter counter">
        <span class="counter__number">16</span>
        <span class="counter__text">awards won</span>
      </div>
      <div class="about__counter counter">
        <span class="counter__number">30</span>
        <span class="counter__text">years experience</span>
      </div>
      <div class="about__counter counter">
        <span class="counter__number">247</span>
        <span class="counter__text">projects completed</span>
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
