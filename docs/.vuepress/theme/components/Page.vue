<template>
  <main class="page">
    <slot name="top" />

    <Content class="theme-default-content" />

    <div class="content-footer" v-if="!isContentStatus">
      <Feedback
        class="content-feedback"
        evtYes="information_helpful"
        evtNo="information_not_helpful"
      />
      <LegacyCallout />
      <PageEdit />
      <PageNav v-bind="{ sidebarItems }" />
    </div>

    <Analytics />

    <slot name="bottom" />
  </main>
</template>

<script>
import PageEdit from '@parent-theme/components/PageEdit.vue'
import PageNav from '@parent-theme/components/PageNav.vue'

import Feedback from './Feedback.vue'
import LegacyCallout from './LegacyCallout.vue'
import Analytics from './Analytics.vue'

export default {
  name: 'Page',
  components: {
    PageEdit,
    PageNav,
    Feedback,
    LegacyCallout,
    Analytics
  },
  props: ['sidebarItems'],
  computed: {
    isContentStatus: function() {
      return !!(this.$frontmatter && this.$frontmatter.issueUrl)
    }
  }
}
</script>

<style lang="stylus" scoped>
.page {
  padding-bottom: 2rem;
  display: block;
}

.content-footer {
  padding-top: 0;
}

.page-edit {
  max-width: 100%;
  padding: 2rem 2rem;
}

.content-feedback {
  padding: 0 2rem;
}

@media (min-width: $MQNarrow) {
  .content-footer {
    padding: 0 2rem;
    padding-top: 0;
  }

  .content-feedback {
    padding: 0;
    margin: 0;
  }

  .page-edit {
    padding: 2rem 0;
  }

  section {
    display: flex;

    .block {
      flex: 1;
    }
  }
}
</style>