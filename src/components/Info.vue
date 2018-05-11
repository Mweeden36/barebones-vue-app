<template>
  <div class="info-container">
    <div class="info">
      <div class="headshot">
        <img alt="My Face" src="../assets/headshot.jpg" />
      </div>
      <div class="header-text">
        <h1>I'm {{ firstName }}. A Software Engineer at
          <a class="header-text-link" v-bind:href="companyLink"
            target="_blank" rel="noopener noreferrer">{{ companyName }}
          </a>.
        </h1>
      </div>
      <a href="mailto:weeden.mike92@gmail.com?Subject=Saw%20Your%20Site"
        class="email-button" target="_top" rel="noopener noreferrer">Let's chat.</a>
    </div>
    <div class="footer">
      <div class="social">
        <a v-bind:href="twitterLink" target="_blank"
          rel="noopener noreferrer" class="fa fa-twitter"> </a>
        <a v-bind:href="githubLink" target="_blank"
          rel="noopener noreferrer" class="fa fa-github"> </a>
        <a v-bind:href="linkedInLink" target="_blank"
          rel="noopener noreferrer" class="fa fa-linkedin"> </a>
      </div>
    </div>
  </div>
</template>

<script>
import Config from '../config.json';

export default {
  name: 'Info',
  data() {
    return {
      ...Config,
    };
  },
};
</script>

<style lang="scss" scoped>
@import '../assets/mixins-and-vars.scss';
.info-container {
  display: inline-block;
  position: relative;
  width: 100%;
  min-height: 500px;
  background-color: $main-color;

  @include tablet-portrait-and-above {
    float: left;
    position: fixed;
    left: 0;
    top: 0;
    height: 100%;
    width: 50%;
  }

  a {
    color: white;
  }

  .info {
    width: 100%;
    margin: 35px 0px 0px 0px;

    @include tablet-portrait-and-above {
      margin: 0;
      position: relative;
      top: 50%;
      transform: translateY(-60%);
    }

    .headshot {
      display: block;
      margin: auto;
      width: 170px;
      height: 170px;
      border-radius: 200px;

      img {
        display: block;
        margin: auto;
        width: 170px;
        height: 170px;
        border-radius: 200px;
        box-shadow: 0 5px 10px $dark-color;
      }
    }
    .header-text {
      display: block;
      margin: 10px auto auto auto;
      padding: 0 20px;
      max-width: 460px;
      color: white;
      font-size: 22px;
      text-align: center;

      h1 {
        font-size: 25px;
        @include tablet-portrait-and-above {
          font-size: 32px;
        }
      }
    }
    .email-button {
      display: block;
      position: relative;
      width: 200px;
      margin: 30px auto auto auto;
      padding: 11px 24px;
      color: white;
      background: $main-color;
      border-color: white;
      border-radius: 3px;
      border-style: solid;
      border-width: 2px;
      font-weight: 700;
      line-height: 22px;
      text-decoration: none;
      text-align: center;
    }
  }
  .footer {
    .social {
      position: absolute;
      right: 20px;
      bottom: 20px;
      height: 27px;

      > a {
        margin-left: 10px;
        padding-top: 4px;
        text-decoration: none;
        float: right;
      }
    }
  }
}
</style>
