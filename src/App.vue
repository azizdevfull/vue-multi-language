<script setup>
import { useI18n } from "vue-i18n";

const { t, locale } = useI18n({ useScope: "global" });
const switchLang = () => {
  console.log(locale.value);
  locale.value === "en" ? (locale.value = "uz") : (locale.value = "en");
  localStorage.setItem("lang", locale.value);
};
</script>

<template>
  <div class="container w-25">
    <form>
      <div class="mb-3">
        <label for="exampleInputEmail1" class="form-label">{{
          $t("placeholders.email")
        }}</label>
        <input
          type="email"
          class="form-control"
          id="exampleInputEmail1"
          aria-describedby="emailHelp"
          :placeholder="$t('placeholders.email')"
        />
        <div id="emailHelp" class="form-text">
          {{ $t("forgot") }}
        </div>
      </div>
      <div class="mb-3">
        <label for="exampleInputPassword1" class="form-label">{{
          $t("placeholders.password")
        }}</label>
        <input
          type="password"
          class="form-control"
          id="exampleInputPassword1"
          :placeholder="$t('placeholders.password')"
        />
      </div>
      <div class="mb-3 form-check">
        <input type="checkbox" class="form-check-input" id="exampleCheck1" />
        <label class="form-check-label" for="exampleCheck1">{{
          $t("checkbox")
        }}</label>
      </div>
      <button type="submit" class="btn btn-primary">
        {{ $t("buttons.login") }}
      </button>
    </form>
    <span class="txt1" @click="switchLang">{{ $t("switch_lang") }}</span>
  </div>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
