<template>
  <Mug>
    <Cold v-if="isIced" />
    <Hot v-else />
    <Contents>
      <template v-slot:top>
        <Creamer v-if="!noCreamer" />
      </template>
      <template v-slot:mid>
        <Syrup v-if="!noSyrup" />
      </template>
      <template v-slot:bottom>
        <Base />
      </template>
    </Contents>
  </Mug>
</template>

<script setup lang="ts">
import Hot      from "./Hot.vue";
import Mug      from "./Mug.vue";
import Base     from "./Base.vue";
import Cold     from "./Cold.vue";
import Syrup    from "./Syrup.vue";
import Creamer  from "./Creamer.vue";
import Contents from "./Contents.vue";

import { computed } from "vue";
import { currentCreamer, currentSyrup } from "../stores/beverage";

type Props = {
  isIced: boolean;
};
defineProps<Props>();

const noCreamer = computed(() => currentCreamer.value.name === "No Creamer");
const noSyrup = computed(() => currentSyrup.value.name === "No Syrup");

</script>
