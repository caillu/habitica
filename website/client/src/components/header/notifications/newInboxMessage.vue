<template>
  <base-notification
    :can-remove="canRemove"
    :has-icon="false"
    :notification="notification"
    :read-after-click="true"
    @click="action"
  >
    <div slot="content">
      <span v-html="$t('userSentMessage', {user: notification.data.sender.name})"></span>
      <div class="notification-small notification-ellipses">
        {{ notification.data.excerpt }}
      </div>
    </div>
  </base-notification>
</template>

<script>
import BaseNotification from './base';

export default {
  components: {
    BaseNotification,
  },
  props: ['notification', 'canRemove'],
  methods: {
    action () {
      this.$root.$emit('bv::show::modal', 'inbox-modal');
    },
  },
};
</script>
