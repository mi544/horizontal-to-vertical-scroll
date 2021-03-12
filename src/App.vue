<template>
  <main>
    <p>
      Chocolate cake sweet roll sesame snaps donut chocolate cake. Bonbon
      macaroon biscuit dragée. Bonbon jelly sesame snaps jelly oat cake dragée
      lemon drops marshmallow. Fruitcake pastry candy canes jelly-o gummi bears
      gummies candy canes. Cake croissant chupa chups ice cream chocolate
      biscuit tiramisu apple pie cheesecake. Cotton candy fruitcake chupa chups
      jujubes cheesecake.
    </p>
    <section class="horizontal-scroll">
      <HorizontalScroll>
        <div class="cards-container">
          <div class="card"></div>
          <div class="card"></div>
          <div class="card"></div>
          <div class="card"></div>
          <div class="card"></div>
        </div>
      </HorizontalScroll>
    </section>
    <p>
      I am oddly aroused by looking for adventure looking for a third I'm just
      in town for the night. Proper grammar I do well dating heyyy it depends on
      the night I'm too lazy to keep typing, it's very hard to meet quality
      women MFA one time in middle school playing devil's advocate The Game.
      Unworthy of serious consideration that's what she said most cats
      eventually love me a fairly successful career in sports I'm a big fan of
      size 2.
    </p>
    <p>
      Toffee cupcake candy canes sugar plum. Chocolate sesame snaps sugar plum
      liquorice ice cream. Ice cream icing donut sweet roll lollipop pastry oat
      cake biscuit sweet roll. Carrot cake caramels soufflé. Gummi bears tootsie
      roll candy biscuit croissant jujubes pie. Pudding pastry danish. Topping
      macaroon lollipop jelly-o icing. Cheesecake chocolate cake macaroon
      biscuit chocolate bar. Icing candy canes muffin jelly beans marzipan
      macaroon marshmallow.
    </p>
  </main>
</template>

<script>
import HorizontalScroll from './components/HorizontalScroll.vue'

export default {
  name: 'App',
  components: { HorizontalScroll }
}
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: sans-serif;
}

p {
  font-size: 1.3rem;
  padding: 1.5rem 20%;
}

.horizontal-scroll {
  position: relative;
  width: 100%;
  min-height: 100vh;
}
.cards-container {
  position: relative;
  height: 100%;
  padding: 0 0 0 150px;
  display: flex;
  flex-flow: row nowrap;
  justify-content: flex-start;
  align-items: center;
}

.card {
  position: relative;
  height: 300px;
  width: 500px;
  background-color: #111f30;
  margin-right: 75px;
  flex-shrink: 0;
}
</style>
