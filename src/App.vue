<template>
  <div id="app">
    <div class="container">
      <section class="teleprompter">
        <article class="teleprompter__card">
          <div class="teleprompter__inner">
            <div class="teleprompter__window">
              <textarea class="teleprompter__textarea">
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit,
                        sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris
                        nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in
                        reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                        pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
                        culpa qui officia deserunt mollit anim id est laborum.
              </textarea>
            </div>
            <ul class="teleprompter__settings list">
              <li class="teleprompter__settings-block">
                <button class="teleprompter__button button button--default">
                  Включить
                </button>
              </li>
              <li class="teleprompter__settings-block">
                <button class="teleprompter__button button button--default is-disabled disabled">
                  <span>Пауза</span>
                </button>
              </li>
              <li class="teleprompter__settings-block">
                <button class="teleprompter__button button button--default is-disabled disabled">
                  Рестарт
                </button>
              </li>
              <li class="teleprompter__settings-block form-field form-field--short">
                <input type="number" class="teleprompter__input form-field__input"
                       max="2" min="1" step="0.5" value="1">
                <label class="teleprompter__label form-field__label">&plusmn;Скорость</label>
              </li>
              <li class="teleprompter__settings-block form-field form-field--short">
                <input type="number" class="teleprompter__input form-field__input"
                       max="32" min="16" value="16">
                <label class="teleprompter__label form-field__label">&plusmn;Шрифт</label>
              </li>
            </ul>
          </div>
        </article>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {

    };
  },
};
</script>

<style lang="scss" scoped>
@import '../src/assets/scss/main.scss';
</style>
