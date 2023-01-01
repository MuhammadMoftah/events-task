<template>
  <main class="myContainer mx-auto box-content">
    <section class="flex">
      <!-- w-14 -->
      <div class="flex flex-col gap-2 w-16 pr-2 items-end">
        <p v-for="(hour, i) in dayArr" :key="hour.value" :id="hour.value">
          <span v-if="i % 2 == 0" class="text-gray-900 font-semibold text-xs">
            {{ hour.title }}
          </span>

          <span v-else class="text-slate-400 font-semibold text-[10px]">
            {{ hour.title }}
          </span>

          <span
            v-if="i % 2 == 0"
            class="text-slate-400 font-semibold text-[10px]"
          >
            {{ hour.value < 180 ? " AM" : " PM" }}
          </span>
        </p>
      </div>

      <aside class="w-full relative bg-[#EDEDED] border-l border-gray-300 px-2">
        <EventCard
          v-for="(event, i) in events"
          :key="event.start"
          :height="getHeight(event)"
          :event="event"
          class="absolute"
          :class="getWidth(event, i)"
          :style="{ top: getTop(event, i) + 'px' }"
        />
      </aside>
    </section>
  </main>
</template>

<script>
import dayArr from "~/data/dayArr.js";
import { events } from "~/data/events.json";
export default {
  data() {
    return {
      dayArr,
      events,
      eventsReady: [],
    };
  },

  mounted() {
    this.getLocation();
  },

  methods: {
    getLocation() {
      this.events.forEach((el, i) => {
        if (i == this.events.length - 1) return;
        if (this.events[i].end > this.events[i + 1].start) {
          this.events[i]["half"] = true;
          this.events[i + 1]["half"] = true;
        }
      });

      console.log(this.events);
    },
    getHeight(event) {
      return event.end - event.start + 8 + "px";
    },
    getWidth(event, i) {
      // event.half && i % 2 == 0
      //         ? retun 'w-1/2'
      //         : event.half && i % 2 != 0
      //         ? 'w-1/2 left-1/2'
      //         : 'w-full'
      return {
        "w-[97%]": true,
        "!w-[48%]": event.half && i % 2 == 0,
        "!w-[48%] left-1/2": event.half && i % 2 != 0,
      };
    },

    getTop(event, i) {
      if (i == 0) {
        return event.start * 1.083333 + 15;
      } else {
        return event.start * 1.083333 + 3;
      }
    },
  },
};
</script>

<style>
.myContainer {
  width: 100%;
  max-width: 600px;
  padding: 16px;
}
</style>
