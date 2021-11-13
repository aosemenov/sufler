<template>
  <div id="app">
    <div class="container">
      <section class="teleprompter">
        <article class="teleprompter__card">
          <div class="teleprompter__inner">
            <div class="teleprompter__window">
              <textarea class="teleprompter__textarea">

              </textarea>
            </div>
            <ul class="teleprompter__settings list">
              <li class="teleprompter__settings-block">
                <button class="teleprompter__button button button--default">
                  Включить
                </button>
              </li>
              <li class="teleprompter__settings-block">
                <button class="teleprompter__button button button--default">
                  Пауза
                </button>
              </li>
              <li class="teleprompter__settings-block">
                <button class="teleprompter__button button button--default">
                  Рестарт
                </button>
              </li>
              <li class="teleprompter__settings-block form-field form-field--short">
                <input class="teleprompter__input form-field__input">
                <label class="teleprompter__label form-field__label">Скорость</label>
              </li>
              <li class="teleprompter__settings-block form-field form-field--short">
                <input class="teleprompter__input form-field__input">
                <label class="teleprompter__label form-field__label">Шрифт</label>
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
};
</script>

<style lang="scss" scoped>
@import '../src/assets/scss/main.scss';
</style>
