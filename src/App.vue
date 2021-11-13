<template>
  <div id="app">
    <div class="container">
      <section class="teleprompter">
        <article class="teleprompter__card">
          <div class="teleprompter__inner">
            <div class="teleprompter__window">
              <textarea class="teleprompter__textarea"
                        ref="textarea"
                        :style="styleObject"
                        :value="dataText.text.message"
              >
              </textarea>
            </div>
            <div class="teleprompter__settings">
              <ul class="teleprompter__settings-list list">
                <li class="teleprompter__settings-item">
                  <button class="teleprompter__button button button--default"
                          @click="scrollTop(currentPosition)"
                          :class="[flagRun ? 'isActive' : '']"
                          :disabled="flagRun"
                  >
                    Включить
                  </button>
                </li>
                <li class="teleprompter__settings-item">
                  <button class="teleprompter__button button button--default"
                          @click="pauseScroll"
                          :class="{isActive: flagPause}"
                  >
                    <span>Пауза</span>
                  </button>
                </li>
                <li class="teleprompter__settings-item">
                  <button class="teleprompter__button button button--default"
                          @click="restartScroll"
                  >
                    Рестарт
                  </button>
                </li>
              </ul>
              <ul class="teleprompter__settings-list list">
                <li class="teleprompter__settings-item form-field form-field--short">
                  <input type="number" class="teleprompter__input form-field__input"
                         max="2" min="1" step="0.5"
                         v-model.number="speedText"
                  >
                  <label class="teleprompter__label form-field__label">&plusmn;Скорость</label>
                </li>
                <li class="teleprompter__settings-item form-field form-field--short">
                  <input type="number" class="teleprompter__input form-field__input"
                         max="32" min="24"
                         v-model.number="fontSize"
                  >
                  <label class="teleprompter__label form-field__label">&plusmn;Шрифт</label>
                </li>
              </ul>
            </div>
          </div>
        </article>
      </section>
    </div>
  </div>
</template>

<script>
import dataText from './data/text';

export default {
  name: 'App',
  data() {
    return {
      speedText: 1,
      fontSize: 24,
      currentPosition: null,
      breakScroll: null,
      flagRun: false,
      flagPause: false,
      dataText,
    };
  },
  methods: {
    scrollTop() {
      this.flagRun = true;
      this.flagPause = false;
      const $textarea = this.$refs.textarea;
      this.breakScroll = setInterval(() => {
        this.currentPosition += this.speedText;
        $textarea.scrollTo({
          top: this.currentPosition,
        });
      }, 10);
    },
    pauseScroll() {
      this.flagRun = false;
      this.flagPause = true;
      clearInterval(this.breakScroll);
    },
    restartScroll() {
      this.flagRun = false;
      this.flagPause = false;
      const $textarea = this.$refs.textarea;
      this.currentPosition = 0;
      $textarea.scrollTo({
        top: this.currentPosition,
        behavior: 'smooth',
      });
      clearInterval(this.breakScroll);
    },
  },
  computed: {
    styleObject() {
      return {
        fontSize: `${this.fontSize}px`,
      };
    },
  },
};
</script>

<style lang="scss" scoped>
@import '../src/assets/scss/main.scss';
</style>
