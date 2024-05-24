<template>
  <q-header elevated class="bg-black text-white flex" height-hint="98">
    <q-toolbar>
      <q-btn
        dense
        flat
        round
        icon="menu"
        @click="this.$emit('toggle-left-drawer')"
      />

      <q-toolbar-title> AG Task Manager </q-toolbar-title>
      <q-btn
        v-on:click="this.$emit('open-new-customer-modal')"
        unelevated
        size="md"
        label="New Customer"
        no-caps
        class="header-btn"
      />
      <q-btn
        v-on:click="this.$emit('open-new-project-modal')"
        unelevated
        size="md"
        label="New Project"
        no-caps
        class="header-btn"
      />
    </q-toolbar>

    <q-tabs align="left" v-model="tabProxy">
      <q-tab name="CREATED" label="Created" v-show="actualProjectId != null">
        <q-badge color="primary">
          {{ createdTasks }}
        </q-badge>
      </q-tab>
      <q-tab
        name="IN_PROGRESS"
        label="In Progress"
        v-show="actualProjectId != null"
      >
        <q-badge color="primary">
          {{ inProgressTasks }}
        </q-badge>
      </q-tab>
      <q-tab name="DONE" label="Done" v-show="actualProjectId != null">
        <q-badge color="primary">
          {{ doneTasks }}
        </q-badge>
      </q-tab>
      <q-tab name="CANCELED" label="Canceled" v-show="actualProjectId != null">
        <q-badge color="primary">
          {{ canceledTasks }}
        </q-badge>
      </q-tab>
    </q-tabs>
  </q-header>
</template>
<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "HeaderComponent",

  props: {
    createdTasks: Number,
    inProgressTasks: Number,
    doneTasks: Number,
    canceledTasks: Number,
    actualProjectId: Number,
  },

  data() {
    return {
      tabProxy: "CREATED",
    };
  },

  watch: {
    tabProxy() {
      this.$emit("update:tab", this.tabProxy);
    },
  },
});
</script>
