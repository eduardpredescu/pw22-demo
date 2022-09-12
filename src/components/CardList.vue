<script lang="ts" setup>
import Card from "./Card.vue";

interface PlanetMarkdown {
  frontmatter: { title: string; image: string; order: number };
  url: string;
}

const allEntries = [...Object.values(import.meta.glob("../pages/*.md"))];

const planets = (
  (await Promise.all(allEntries.map((fn) => fn()))) as PlanetMarkdown[]
).sort((a, b) => a.frontmatter.order - b.frontmatter.order);
</script>

<template>
  <div class="flex justify-center items-center">
    <div class="flex w-full flex-wrap">
      <Card
        v-for="item in planets"
        :key="item.frontmatter.title"
        :image="item.frontmatter.image"
        :name="item.frontmatter.title"
        :link="item.url"
      />
    </div>
  </div>
</template>
