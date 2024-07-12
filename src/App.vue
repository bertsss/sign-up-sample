<template>
    <div class="app-container">
        <AppSteps :step="1"></AppSteps>

        <div class="main-container">
            <AppForm class="form"></AppForm>
            <AppAds class="ads"></AppAds>
        </div>
        <AppFooter></AppFooter>
    </div>
</template>

<script>
import AppSteps from './components/AppSteps.vue'
import AppForm from './components/AppForm.vue'
import AppAds from './components/AppAds.vue'
import AppFooter from './components/AppFooter.vue'

export default {
  name: 'App',
  components: {
    AppSteps,
    AppForm,
    AppAds,
    AppFooter
  }
}
</script>

<style lang="scss" scoped>

.app-container {
    padding: 10px 20px;

    .main-container {
        display: flex;
        justify-content: center;
        margin-bottom: 30px;

        @media only screen and (max-width: 1280px) {
            flex-direction: column;
        }

        .form {
            max-width: 700px;
            margin-right: 20px;

            @media only screen and (max-width: 1280px) {
                width: 100%;
                max-width: unset;
                margin-bottom: 30px;
            }
        }

        .ads {
            max-width: 500px;

            @media only screen and (max-width: 1280px) {
                width: 100%;
                max-width: unset;
            }
        }
    }
}

@media only screen and (min-width: 1280px) {
}
</style>
