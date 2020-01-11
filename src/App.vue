<template>
  <div class="overflow-auto">
    <h1 class="title">HildaMari Discord Bot Documentation</h1>
    <b-button href="http://join.hilda.pw/" variant="primary">HildaMari Support Server</b-button>
    <b-tabs pills align="center" justified content-class="mt-3">
      <b-tab title="Hilda" id="hilda"><Hilda /></b-tab>
      <b-tab title="Marianne" id="marianne"><Marianne /></b-tab>
    </b-tabs>
  </div>
</template>

<style>
@font-face {
  font-family: "Athelas";
  src: url('./assets/fonts/Athelas-Regular.ttf');
}

@font-face {
  font-family: "Garamond";
  src: url('./assets/fonts/subset-GaramondPremrPro.ttf');
}

@font-face {
  font-family: "GaramondBd";
  src: url('./assets/fonts/subset-GaramondPremrPro-Bd.ttf');
}

body {
  padding: 1rem;
  background-image: url("./assets/trans.png");
  background-size: cover;
  
}

.overflow-auto {
  font-family: "Athelas";
}

.title {
  text-align: center;
  font-family: "GaramondBd";
}

.jumbotron {
  text-align: center;
}

#marianne___BV_tab_button__.nav-link, #hilda___BV_tab_button__.nav-link {
  font-family: "GaramondBd";
}
</style>

<style lang="scss">
  @import 'assets/scss/_custom.scss';

  @import "~bootstrap/scss/bootstrap.scss";
  @import '~bootstrap-vue/dist/bootstrap-vue.css';

  #marianne___BV_tab_button__.nav-link {
    background-color: var(--blue);
    color: var(--text-dark);
  }

  #hilda___BV_tab_button__.nav-link {
    background-color: var(--pink);
    color: var(--text-dark);
  }
</style>

<script>
import Hilda from './components/Hilda.vue'
import Marianne from './components/Marianne.vue'

export default {
  components: {
    Hilda, Marianne
  }
};
</script>