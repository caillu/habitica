<template>
  <div
    class="modal-footer"
    style="margin-top:0"
    ng-init="loadWidgets()"
  >
    <div class="container-fluid share-buttons">
      <div class="row">
        <div class="col-12 text-center">
          <a
            class="twitter-share-button share-button"
            :href="twitterLink"
            target="_blank"
          >
            <div
              class="social-icon twitter svg-icon"
              v-html="icons.twitter"
            ></div>
            {{ $t('tweet') }}
          </a>
          <a
            class="fb-share-button share-button"
            :href="facebookLink"
            target="_blank"
          >
            <div
              class="social-icon facebook svg-icon"
              v-html="icons.facebook"
            ></div>
            {{ $t('share') }}
          </a>
          <!-- @TODO: Still want this?
            .col-4a.tumblr-share-button(:data-href='socialLevelLink', data-notes='none')-->
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .share-buttons {
    margin-top: 1em;
    margin-bottom: 1em;
  }

  .share-button {
    display: inline-block;
    width: 77px;
    padding: .5em;
    border-radius: 2px;
    text-align: center;
    color: #fff;
  }

  .fb-share-button {
    background-color: #2995cd;
  }

  .twitter-share-button {
    margin-right: .5em;
    background-color: #3bcad7;
  }

  .social-icon {
    width: 16px;
    display: inline-block;
    vertical-align: bottom;
    margin-right: .5em;
  }

  .social-icon.facebook svg {
    width: 7.5px;
    margin-bottom: .2em;
  }

  .social-icon.twitter {
    margin-bottom: .2em;
  }
</style>

<script>
// @TODO:
import twitter from '@/assets/svg/twitter.svg';
import facebook from '@/assets/svg/facebook.svg';

const BASE_URL = 'https://habitica.com';

export default {
  data () {
    const tweet = this.$t('achievementShare');

    return {
      icons: Object.freeze({
        twitter,
        facebook,
      }),
      tweet,
      achievementLink: `${BASE_URL}`,
      twitterLink: `https://twitter.com/intent/tweet?text=${tweet}&via=habitica&url=${BASE_URL}&count=none`,
      facebookLink: `https://www.facebook.com/sharer/sharer.php?text=${tweet}&u=${BASE_URL}`,
    };
  },
};
</script>
