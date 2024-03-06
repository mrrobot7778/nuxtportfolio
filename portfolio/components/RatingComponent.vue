<template>
   <div class="rating">
      <div class="default" v-show="defaultVal">
        <button><IconsEmptyStar @mouseover="{defaultVal = false;rt1Hovered = true}"/></button>
        <button><IconsEmptyStar @mouseover="{defaultVal = false;rt2Hovered = true}"/></button>
        <button><IconsEmptyStar @mouseover="{defaultVal = false;rt3Hovered = true}"/></button>
        <button><IconsEmptyStar @mouseover="{defaultVal = false;rt4Hovered = true}"/></button>
        <button><IconsEmptyStar @mouseover="{defaultVal = false;rt5Hovered = true}"/></button>
      </div>
      <div class="hoverStates">
      <div v-show="rt1Hovered">
        <button @mouseleave="{rt1Hovered = false;defaultVal=true}" @click="handleClick" v-if="clicked === false" ><IconsFullStar/></button>
        <button v-else><IconsFullStar/></button>
        <button><IconsEmptyStar/></button>
        <button><IconsEmptyStar/></button>
        <button><IconsEmptyStar/></button>
        <button><IconsEmptyStar/></button>
      </div>
      <div v-show="rt2Hovered">
        <button><IconsFullStar/></button>
        <button @mouseleave="{rt2Hovered = false;defaultVal=true}" @click="handleClick" v-if="clicked === false"><IconsFullStar/></button>
        <button v-else><IconsFullStar/></button>
        <button><IconsEmptyStar/></button>
        <button><IconsEmptyStar/></button>
        <button><IconsEmptyStar/></button>
      </div>
      <div v-show="rt3Hovered">
        <button><IconsFullStar/></button>
        <button><IconsFullStar/></button>
        <button @mouseleave="{rt3Hovered = false;defaultVal=true}" @click="handleClick" v-if="clicked === false"><IconsFullStar/></button>
        <button v-else><IconsFullStar/></button>
        <button><IconsEmptyStar/></button>
        <button><IconsEmptyStar/></button>
      </div>
      <div v-show="rt4Hovered">
        <button><IconsFullStar/></button>
        <button><IconsFullStar/></button>
        <button><IconsFullStar/></button>
        <button @mouseleave="{rt4Hovered = false;defaultVal=true}" @click="handleClick"  v-if="clicked === false"><IconsFullStar/></button>
        <button v-else><IconsFullStar/></button>
        <button><IconsEmptyStar/></button>
      </div>
      <div v-show="rt5Hovered">
        <button><IconsFullStar/></button>
        <button><IconsFullStar/></button>
        <button><IconsFullStar/></button>
        <button><IconsFullStar/></button>
        <button  @mouseleave="{rt5Hovered = false;defaultVal=true}" @click="handleClick"  v-if="clicked === false"><IconsFullStar/></button>
        <button v-else><IconsFullStar/></button>
      </div>
    </div>
   </div>
</template>

<script setup>

    const defaultVal = ref(true)
    const rateElement = ref(false)
    const rt1Hovered = ref(false)
    const rt2Hovered = ref(false)
    const rt3Hovered = ref(false)
    const rt4Hovered = ref(false)
    const rt5Hovered = ref(false)
    let clicked = ref(false)

    const handleClick = () => {
      clicked.value = true;
    }
  

</script>

<style>
  .ratingComponent {
    display:flex;
  }

  .rating button {
    border:0;
  }
</style>