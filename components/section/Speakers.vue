<script lang="ts" setup>
import { speakersData } from "~/data.json";
</script>
<template>
  <AppSection title="Speakers">
    <div class="flex flex-wrap items-stretch justify-center gap-8">
      <div
        class="flex-[0_0_100%] md:flex-[0_0_calc(50%-1rem)] lg:flex-[0_0_calc(25%-1.5rem)]"
        v-for="(data, index) in speakersData"
        :key="index"
      >
        <UCard class="h-full">
          <div class="flex flex-col justify-center items-center">
            <img
              class="rounded-full size-32 mb-4 object-cover"
              :src="data.profile"
              alt="Avatar"
            />
            <p class="text-xl font-bold">{{ data.name }}</p>
            <p class="text-center opacity-95">{{ data.rank }}</p>
            <p class="text-center opacity-75 mb-2">
              {{ data.description }}
            </p>
            <span class="flex gap-2 items-center">
              <a v-if="data.linkedin" :href="data.linkedin">
                <UIcon
                  name="radix-icons:linkedin-logo"
                  class="size-5 opacity-75 cursor-pointer"
                />
              </a>
              <a v-if="data.email" :href="`mailto:${data.email}`">
                <UIcon
                  name="tabler:mail-filled"
                  class="size-5 opacity-75 cursor-pointer"
                />
              </a>
            </span>
          </div>
        </UCard>
      </div>
    </div>
  </AppSection>
</template>
