<template>
  <div class="sidebar"
       :data="backgroundColor">
    <!--
            Tip 1: you can change the color of the sidebar's background using: data-background-color="white | black | darkblue"
            Tip 2: you can change the color of the active button using the data-active-color="primary | info | success | warning | danger"
        -->
    <!-- -->
    <div class="sidebar-wrapper" id="style-3">
      <div class="logo">
        <a href="/" class="simple-text logo-mini">
          <div class="logo-img"
               :class="{'logo-img-rtl': $rtl.isRTL}">
            <img
              src="data:image/jpeg;base64,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"
              alt="">
          </div>
        </a>
        <a href="/" class="simple-text logo-normal">
          {{title}}
        </a>
      </div>
      <slot>

      </slot>
      <ul class="nav">
        <!--By default vue-router adds an active class to each route link. This way the links are colored when clicked-->
        <slot name="links">
          <sidebar-link v-for="(link,index) in sidebarLinks"
                        :key="index"
                        :to="link.path"
                        :name="link.name"
                        :icon="link.icon">
          </sidebar-link>
        </slot>
      </ul>
    </div>
  </div>
</template>
<script>
  import SidebarLink from "./SidebarLink";

  export default {
    props: {
      title: {
        type: String,
        default: "Disaster Management"
      },
      backgroundColor: {
        type: String,
        default: "vue"
      },
      activeColor: {
        type: String,
        default: "success",
        validator: value => {
          let acceptedValues = [
            "primary",
            "info",
            "success",
            "warning",
            "danger"
          ];
          return acceptedValues.indexOf(value) !== -1;
        }
      },
      sidebarLinks: {
        type: Array,
        default: () => []
      },
      autoClose: {
        type: Boolean,
        default: true
      }
    },
    provide() {
      return {
        autoClose: this.autoClose,
        addLink: this.addLink,
        removeLink: this.removeLink
      };
    },
    components: {
      SidebarLink
    },
    computed: {
      /**
       * Styles to animate the arrow near the current active sidebar link
       * @returns {{transform: string}}
       */
      arrowMovePx() {
        return this.linkHeight * this.activeLinkIndex;
      },
      shortTitle() {
        return this.title.split(' ')
          .map(word => word.charAt(0))
          .join('').toUpperCase();
      }
    },
    data() {
      return {
        linkHeight: 65,
        activeLinkIndex: 0,
        windowWidth: 0,
        isWindows: false,
        hasAutoHeight: false,
        links: []
      };
    },
    methods: {
      findActiveLink() {
        this.links.forEach((link, index) => {
          if (link.isActive()) {
            this.activeLinkIndex = index;
          }
        });
      },
      addLink(link) {
        const index = this.$slots.links.indexOf(link.$vnode);
        this.links.splice(index, 0, link);
      },
      removeLink(link) {
        const index = this.links.indexOf(link);
        if (index > -1) {
          this.links.splice(index, 1);
        }
      }
    },
    mounted() {
      this.$watch("$route", this.findActiveLink, {
        immediate: true
      });
    }
  };
</script>
