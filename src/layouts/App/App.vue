<template>
  <Global />

  <Header />

  <div class="max-w-screen-lg px-4 py-10 mx-auto">
    <h2 class="text-title">Cards</h2>

    <List :sizes="sizes">
      <Card
        v-for="card in cards"
        :key="card.id"
        :title="card.title"
        :subtitle="card.subtitle"
        :icon="card.icon"
      >
        <p v-if="card.content" v-html="card.content" />
      </Card>
    </List>

    <h2 class="mt-10 text-title">Buttons</h2>

    <List :sizes="sizes" direction="column">
      <Button>Normal Button</Button>
      <Button full
        >Full Button with <strong class="text-bold">Bold</strong> Text</Button
      >
    </List>
  </div>
</template>

<script setup>
import Global from '~/components/organisms/global/Global.vue'
import Header from '~/components/organisms/header/Header.vue'
import List from '~/components/molecules/list/List.vue'
import Card from '~/components/atoms/card/Card.vue'
import Button from '~/components/atoms/button/Button.vue'
import { load } from '~/plugins/mode'
import { cards } from './App.data'

load()

const sizes = {
  sm: 1 / 1,
  md: 1 / 2,
  lg: 1 / 3,
  xl: 1 / 3,
}
</script>
