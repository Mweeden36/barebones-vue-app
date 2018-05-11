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

<style lang="scss" scoped>
  @import '../assets/mixins-and-vars.scss';

  .resume-container {
    display: inline-block;
    padding: 25px 25px 80px;

    @include tablet-portrait-and-above {
      float: right;
      top: 0;
      right: 0;
      width: 45%;
      overflow-x: hidden;
    }

    .resume-section {
      clear: both;
      display: block;
      overflow: auto;
      margin-top: 25px;
      .section-name {
        margin: 0 0 20px 0;
        font-size: 12px;
        font-weight: 600;
        letter-spacing: 1px;
        text-transform: uppercase;
        color: $dark-color;
      }
      .text {
        line-height: 25px;
        p {
          margin: 0;
          color: #313131;
          font-weight: 400;
          word-wrap: break-word;
        }
      }
      .list {
        clear: both;
        padding: 0;
        list-style-type: none;

        li {
          margin-bottom: 10px;
          font-weight: 700;

          &::before {
            position: relative;
            bottom: 0.2ex;
            margin-right: 20px;
            content: "";
            font-family: "FontAwesome";
            font-size: 8px;
          }
        }
      }
      .experience-member {
        margin-bottom: 20px;
        height: 40px;

        .experience-member-info {
          float: left;
          .company {
            font-weight: 700;
            line-height: 25px;
            display: block;
          }
          .position {
            max-width: 50%;
          }
        }
        .experience-date {
          float: right;
          font-weight: 700;
          line-height: 25px;
        }
      }
      .table-display {
        display: table;
        width: 100%;
        padding-bottom: 10px;
        .table-row {
          display: table-row;

          &.overview {
            font-weight: 700;
          }
          .table-detail {
            display: table-cell;

            &.date {
              width: 105px;
              text-align: right;
            }
          }
        }
      }
    }
  }
</style>
