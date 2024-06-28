<!-- src/components/Calendar.vue -->
<template>
  <div>
    <vue-cal
      :events="events"
      :available-views="['month']"
      @view-change="fetchEvents"
    />
  </div>
</template>

<script>
import VueCal from 'vue-cal';
import 'vue-cal/dist/vuecal.css';

export default {
  components: {
    VueCal
  },
  data() {
    return {
      events: []
    };
  },
  methods: {
    async fetchEvents(view) {
      try {
        // Replace with your API endpoint
        const response = await fetch(`559a3d19d1mshd5d92a81185b528p102bb8jsn268d17c01119`);
        const data = await response.json();
        this.events = data.events.map(event => ({
          start: event.start_date,
          end: event.end_date,
          title: event.title
        }));
      } catch (error) {
        console.error('Error fetching events:', error);
      }
    }
  },
  mounted() {
    this.fetchEvents({
      start: new Date(),
      end: new Date(new Date().setDate(new Date().getDate() + 30))
    });
  }
};
</script>
