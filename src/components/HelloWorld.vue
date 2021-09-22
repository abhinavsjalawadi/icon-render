<template>
  
  <div>
    <li v-for="(path, key)  in iconMap" :key="key">

      {{key}}
      <svg
        xmlns="http://www.w3.org/2000/svg"
        :viewBox="viewBox"
        :aria-labelledby="icon"
        :height="height"
        :width="width"
        role="presentation"
        class="vp-icon--svg"
        @click="$emit('click', $event)"
      >
        <g
          v-html="iconMap[key].path || path"
        />
      </svg>
      
    </li>
  </div>

</template>

<script>
  import { icons } from '../assets/icons.js';
  export default {
    data: () => ({
      iconMap: icons,
      // styleObject: {
      //   display: 'flex',
      //   flexDirection: 'column'
      // }
    }),
    name: 'HelloWorld',
    props: {
      icon: {
        type: String,
        default: 'bell'
      },
      size: {
        type: [Number, String],
        default: 14
      },
      iconColor: {
        type: String,
        default: 'currentColor'
      },
      flag: {
        type: Boolean,
        default: false
      }
    },
    mounted() {
    },
    computed: {
      viewBox() {
        // const { icon, iconMap, size } = this;
        // if (iconMap[icon] && iconMap[icon].viewBox) {
        //           console.log(iconMap)

        //   return iconMap[icon].viewBox;
        // }
        return `0 0 ${40} ${40}`;
        // return 0
      },
      height() {
        // const { icon, iconMap, size } = this;
        // if (iconMap[icon] && iconMap[icon].viewBox) {
        //   return iconMap[icon].height;
        // }
        return "500px";
      },
      width() {
        // const { icon, iconMap, size } = this;
        // if (iconMap[icon] && iconMap[icon].viewBox) {
        //   return iconMap[icon].width;
        // }
        return "500px";
      }
    }
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
  .vp-icon--svg {
    height: 8em;
    vertical-align: middle;
  }
</style>
