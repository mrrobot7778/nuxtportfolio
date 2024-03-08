<template>
  <div class="rating py-4">
     <div class="default" v-show="defaultVal">
       <button><IconsEmptyStar @mouseover="{defaultVal = false;rt1Hovered = true}"/></button>
       <button><IconsEmptyStar @mouseover="{defaultVal = false;rt2Hovered = true}"/></button>
       <button><IconsEmptyStar @mouseover="{defaultVal = false;rt3Hovered = true}"/></button>
       <button><IconsEmptyStar @mouseover="{defaultVal = false;rt4Hovered = true}"/></button>
       <button><IconsEmptyStar @mouseover="{defaultVal = false;rt5Hovered = true}"/></button>
     </div>
     <div class="hoverStates">
     <div v-show="rt1Hovered">
       <button @mouseleave="{rt1Hovered = false;defaultVal=true}" @click="handleClick(1)" v-if="clicked === false && rated === false" ><IconsFullStar/></button>
       <button v-else><IconsFullStar/></button>
       <button><IconsEmptyStar/></button>
       <button><IconsEmptyStar/></button>
       <button><IconsEmptyStar/></button>
       <button><IconsEmptyStar/></button>
     </div>
     <div v-show="rt2Hovered">
       <button><IconsFullStar/></button>
       <button @mouseleave="{rt2Hovered = false;defaultVal=true}" @click="handleClick(2)" v-if="clicked === false && rated === false"><IconsFullStar/></button>
       <button v-else><IconsFullStar/></button>
       <button><IconsEmptyStar/></button>
       <button><IconsEmptyStar/></button>
       <button><IconsEmptyStar/></button>
     </div>
     <div v-show="rt3Hovered">
       <button><IconsFullStar/></button>
       <button><IconsFullStar/></button>
       <button @mouseleave="{rt3Hovered = false;defaultVal=true}" @click="handleClick(3)" v-if="clicked === false && rated === false"><IconsFullStar/></button>
       <button v-else><IconsFullStar/></button>
       <button><IconsEmptyStar/></button>
       <button><IconsEmptyStar/></button>
     </div>
     <div v-show="rt4Hovered">
       <button><IconsFullStar/></button>
       <button><IconsFullStar/></button>
       <button><IconsFullStar/></button>
       <button @mouseleave="{rt4Hovered = false;defaultVal=true}" @click="handleClick(4)"  v-if="clicked === false && rated === false"><IconsFullStar/></button>
       <button v-else><IconsFullStar/></button>
       <button><IconsEmptyStar/></button>
     </div>
     <div v-show="rt5Hovered">
       <button><IconsFullStar/></button>
       <button><IconsFullStar/></button>
       <button><IconsFullStar/></button>
       <button><IconsFullStar/></button>
       <button  @mouseleave="{rt5Hovered = false;defaultVal=true}" @click="handleClick(5)"  v-if="clicked === false && rated === false"><IconsFullStar/></button>
       <button v-else><IconsFullStar/></button>
     </div>
   </div>
  </div>
</template>

<script setup>

  const defaultVal = ref(true);
  const rt1Hovered = ref(false);
  const rt2Hovered = ref(false);
  const rt3Hovered = ref(false);
  const rt4Hovered = ref(false);
  const rt5Hovered = ref(false);
  const rated = ref(false)
  const clicked = ref(false);
  const routeSlug = useRoute().params.slug;

  const handleClick = (rateValue) => {

    const ratings = JSON.parse(localStorage.getItem("ratings")) || [];
    const existingRate = ratings.find(rate => rate.slug === routeSlug);
    if (!existingRate) {
      clicked.value = true;
      ratings.push({
        slug: routeSlug,
        rateValue: rateValue
      });
      localStorage.setItem("ratings", JSON.stringify(ratings));
    }
    
  };

  onBeforeMount(() => {

    let ratings = JSON.parse(localStorage.getItem("ratings")) || [];
    let rateObj;
    let rateValue = null;

    if (ratings && ratings.length) {
      rateObj = ratings.find(rate => rate.slug === routeSlug);
      rateValue = rateObj?.rateValue || null;
    }

    if (rateValue === 1) {
      rt1Hovered.value = true;
      defaultVal.value = false;
      rated.value = true;
    } else if (rateValue === 2) {
      rt2Hovered.value = true;
      defaultVal.value = false;
      rated.value = true;
    } else if (rateValue === 3) {
      rt3Hovered.value = true;
      defaultVal.value = false;
      rated.value = true;
    } else if (rateValue === 4) {
      rt4Hovered.value = true;
      defaultVal.value = false;
      rated.value = true;
    } else if (rateValue === 5) {
      rt5Hovered.value = true;
      defaultVal.value = false;
      rated.value = true;
    }
  });
</script>

<style>
    
  .ratingComponent {
    display:flex;
  }

  .rating button {
    border:0;
  }
 
</style>