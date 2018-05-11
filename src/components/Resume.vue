<template>
  <div class="resume-container">
    <div class="resume">
      <div class="resume-section about">
        <div class="section-name">
          <p>About me</p>
        </div>
        <div class="text">
          <p>{{ aboutBlurb }}</p>
        </div>
      </div>
      <div class="resume-section skills">
        <div class="section-name">
          <p>Skills</p>
        </div>
        <div class="text">
          <p>Here are some of the languages, libraries and tools I use:</p>
        </div>
        <ul class="list">
          <li v-for="skill in skills" v-bind:key="skill">
            {{ skill }}
          </li>
        </ul>
      </div>
      <div class="resume-section experience">
        <div class="section-name">
          <p>Experience</p>
        </div>
        <div v-for="job in employmentHistory"
          v-bind:key="job.company + job.jobTitle"
          class="table-display">
          <div class="table-row overview">
            <div class="table-detail">{{ job.companyName }}</div>
            <div class="table-detail date">{{ job.date }}</div>
          </div>
          <div class="table-row">{{ job.jobTitle }}</div>
        </div>
      </div>
      <div class="resume-section education">
        <div class="section-name">
          <p>Education</p>
        </div>
        <div class="table-display">
          <div class="overview table-row">
            <div class="college table-detail">{{ education.schoolName }}</div>
            <div class="date table-detail">{{ education.date }}</div>
          </div>
          <div class="details table-row">{{ education.degreeName }}</div>
          <div class="details table-row">3.33 GPA - <i>Cum Laude</i></div>
          <div class="details table-row">{{ education.honors }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { resume } from '../config.json';

export default {
  name: 'Resume',
  data() {
    return {
      ...resume,
    };
  },
};
</script>

<style scoped>
h1 {
  font-weight: normal;
}
</style>
