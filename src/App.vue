<script>
import Data from './components/Data.vue'
import Demo1 from './components/Demo1.vue';
import Demo2 from './components/Demo2.vue';
import ReplaceMethodWithRef from './components/ReplaceMethodWithRef.vue';
import ReplaceMethodWithReactive from './components/ReplaceMethodWithReactive.vue';
import VModel from './components/VModel.vue';
import ReplacingComputedProps from './components/ReplacingComputedProps.vue';
import ReplacingWatchers from './components/ReplacingWatchers.vue';
export default {
  components: {
    Data,
    Demo1,
    Demo2,
    ReplaceMethodWithRef,
    ReplaceMethodWithReactive,
    VModel,
    ReplacingComputedProps,
    ReplacingWatchers,

  }
}
</script> 

<template>
  <div>
    <ReplacingWatchers />
    <Data />
    <Demo1 />
    <Demo2 />
    <ReplaceMethodWithRef />
    <ReplaceMethodWithReactive />
    <ReplacingComputedProps />

    <VModel />

  </div>
</template>

