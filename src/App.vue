<script setup>
import { computed, ref } from "vue";

let timeout;

const components = [
  // Form
  "AutoComplete",
  "Calendar",
  "CascadeSelect",
  "Checkbox",
  "Chips",
  "ColorPicker",
  "Dropdown",
  "Editor",
  "InputGroup",
  "InputMask",
  "InputNumber",
  "InputSwitch",
  "InputText",
  "Knob",
  "Listbox",
  "MultiSelect",
  "Password",
  "RadioButton",
  "Rating",
  "SelectButton",
  "Slider",
  "Textarea",
  "ToggleButton",
  "TreeSelect",
  "TriStateCheckbox",

  // Button
  "Button",
  "SpeedDial",
  "SplitButton",

  // Data
  "DataTable",
  "DataView",
  "OrderList",
  "OrgChart",
  "Paginator",
  "PickList",
  "Tree",
  "TreeTable",
  "Timeline",
  "VirtualScroller",

  // Panel
  "Accordion",
  "Card",
  "Deferred",
  "Divider",
  "Fieldset",
  "Panel",
  "ScrollPanel",
  "Splitter",
  "TabView",
  "Toolbar",

  // Overlay
  "ConfirmDialog",
  "ConfirmPopup",
  "Dialog",
  "DynamicDialog",
  "OverlayPanel",
  "Sidebar",
  "Tooltip",

  // File
  "Upload",

  // Menu
  "Breadcrumb",
  "ContextMenu",
  "Dock",
  "Menu",
  "Menubar",
  "MegaMenu",
  "PanelMenu",
  "Steps",
  "TabMenu",
  "TieredMenu",

  // Chart
  "Chart.js",

  // Messages
  "Message",
  "InlineMessage",
  "Toast",

  // Media
  "Carousel",
  "Galleria",
  "Image",

  // Misc
  "Avatar",
  "Badge",
  "BlockUI",
  "Chip",
  "FocusTrap",
  "Inplace",
  "ScrollTop",
  "Skeleton",
  "ProgressBar",
  "ProgressSpinner",
  "Ripple",
  "StyleClass",
  "Tag",
  "Terminal",
];
const handleMouseOver = (event) => {
  if (!timeout) {
    timeout = setTimeout(() => {
      document.documentElement.style.setProperty(
        "--cursorX",
        `${event.clientX}px`
      );
      document.documentElement.style.setProperty(
        "--cursorY",
        `${event.clientY}px`
      );
      timeout = null;
    }, 16);
  }
};
const repeatedComponents = computed(() => {
  let arr = [];
  for (let i = 0; i < 20; i++) {
    arr = arr.concat(components);
  }
  return arr;
});
</script>

<template>
  <div class="main" @mousemove="handleMouseOver">
    <div class="bg-logo-shadow"></div>
    <img
      src="./assets/primevue-bg-logo.svg"
      class="bg-logo"
      alt="PrimeVue logo"
    />
    <div class="background">
      <span
        v-for="(component, index) in repeatedComponents"
        :key="index"
        class="component-name"
      >
        {{ component }}
      </span>
    </div>
    <div class="card">
      <a href="https://primevue.org/" target="_blank">
        <img
          src="./assets/primevue-icon.svg"
          class="logo vue"
          alt="PrimeVue logo"
        />
      </a>
      <h1>Tailwind CSS Based UI Component Library for Vue.js</h1>
      <p>
        PrimeVue team is working on a brand new customizable preset implemented
        with Tailwind CSS.
      </p>
      <div class="pbar-wrapper">
        <div class="pbar">
          <div class="pbar-shadow-wrapper">
            <div class="pbar-value"></div>
          </div>
        </div>
      </div>
      <span>Coming Soon!</span>
    </div>
  </div>
</template>

<style scoped>
:root {
  --cursorX: 0;
  --cursorY: 0;
}

.main {
  position: relative;
  overflow: hidden;
}

.bg-logo {
  position: absolute;
  width: 700px;
  opacity: 0.35;
  z-index: 0;
  pointer-events: none;
  filter: drop-shadow(0 0 2em #6cc89f4b);
}


.background {
  will-change: background;
  position: absolute;
  top: 0;
  left: -50px;
  width: 150vw;
  height: 100%;
  z-index: -1;
  background: radial-gradient(
    circle at var(--cursorX) var(--cursorY),
    rgba(175, 231, 194, 0.25),
    transparent 20%
  );
  overflow: hidden;
}

.background span {
  display: inline-block;
  margin: 0.5em;
  font-size: 1.2em;
  color: rgba(227, 238, 230, 0.22);
  transition: color 0.3s;
  will-change: color;
  opacity: 0.4;
  mix-blend-mode: color-burn;
  user-select: none;
}

.logo {
  height: 6em;
  padding: 1.5em 1.5em 1em;
  will-change: filter;
  transition: filter 300ms;
}

.logo.vue:hover {
  filter: drop-shadow(0 0 1em #42b88367);
}
</style>
