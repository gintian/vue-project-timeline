<template>
  <ul class="project-timeline-team">
    <li
      v-for="(member, index) in members"
      :key="`${member.name}-${index}`"
      class="project-timeline-team__item"
    >
      <img
        v-if="member.avatar"
        class="project-timeline-team__avatar"
        :src="member.avatar"
        :alt="member.name"
        :title="member.name"
      >
      <span
        v-else
        class="project-timeline-team__name"
      >
        {{ member.name }}
      </span>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'ProjectTimelineTeam',

  props: {
    members: {
      type: Array,
      required: true
    }
  }
}
</script>

<style>
.project-timeline-team {
  display: flex;
  flex-wrap: wrap;
  margin: 0.5em 0 0;
  padding: 0;
  list-style: none;
}

.project-timeline-team__item {
  margin-right: 0.5em;
}

.project-timeline-team__avatar {
  vertical-align: middle;
  border-radius: 50%;
}
</style>
