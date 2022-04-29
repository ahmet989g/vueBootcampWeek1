<template>
  <div>
    <header>Class List App</header>
    <div class="container">
      <div class="class--list--app">
        <div class="card">
          <ul class="class-list">
            <li>
              <label>
                <input class="mr-5" v-model="styles.bgColor" type="checkbox" />
                <span>Background Color</span>
              </label>
            </li>
            <li>
              <label>
                <input class="mr-5" v-model="styles.border" type="checkbox" />
                <span>Border</span>
              </label>
            </li>
            <li>
              <label>
                <input class="mr-5" v-model="styles.borderRadius" type="checkbox" />
                <span>Border Radius</span>
              </label>
            </li>
            <li>
              <label>
                <input class="mr-5" v-model="styles.color" type="checkbox" />
                <span>Color</span>
              </label>
            </li>
            <li>
              <label>
                <input class="mr-5" v-model="styles.fontBold" type="checkbox" />
                <span>Font Bold</span>
              </label>
            </li>
            <li>
              <label>
                <input class="mr-5" v-model="styles.fontItalic" type="checkbox" />
                <span>Font Italic</span>
              </label>
            </li>
          </ul>

          <textarea :class="textAreaClass" rows="5"></textarea>
        </div>
      </div>
    </div>
  </div>
</template>
<style>
      .bgColor {
        background-color: #1565c0;
      }
      .border {
        border: 5px solid #ffff00;
      }
      .borderRadius {
        border-radius: 10px;
      }
      .color {
        color: #ffff00;
      }
      .fontBold {
        font-weight: bold;
      }
      .fontItalic {
        font-style: italic;
      }
    </style>
<script>
export default {
  data() {
    return {
      styles: {
        bgColor: false,
        border: false,
        borderRadius: false,
        color: false,
        fontBold: false,
        fontItalic: false,
      },
    };
  },
  computed: {
    textAreaClass() {
      return {
        bgColor: this.styles.bgColor,
        border: this.styles.border,
        borderRadius: this.styles.borderRadius,
        color: this.styles.color,
        fontBold: this.styles.fontBold,
        fontItalic: this.styles.fontItalic,
      };
    },
  },
}
</script>

