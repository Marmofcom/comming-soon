<script setup lang="ts">
import {useUserStore} from '~/stores/user'

const user = useUserStore()
const name = ref(user.savedName)

const router = useRouter()
const notifyMe = () => {

}

const {t} = useI18n()
</script>

<template>
  <div relative>
    <div text-4xl mb-3 flex justify-center>
      <img src="/logo.svg" dark:hidden class="w-32" alt="">
      <img src="/logo-dark.svg" hidden dark:block class="w-32" alt="">
    </div>
    <h1 text-5xl dark:text-gray-400>{{ t('intro.desc') }} <span text-black dark:text-white>{{ t('intro.soon')}}</span></h1>
    <p text-xl>
      {{ t('intro.subscribe-and-get-notified') }}
    </p>
    <div my-10 flex flex-col sm:flex-row items-center justify-center space-y-3 sm:space-y-0 sm:space-x-3>

      <div>
        <input
            id="input"
            v-model="name"
            :placeholder="t('intro.whats-your-email-address')"
            :aria-label="t('intro.whats-your-email-address')"
            type="text"
            autocomplete="false"
            p="x4 y2"
            w="250px"
            text="center"
            dark:bg="transparent"
            border="~ rounded gray-400 dark:gray-700"
            outline="none active:none"
            @keydown.enter="go"
        >
        <label class="hidden" for="input">{{ t('intro.whats-your-name') }}</label>

      </div>
      <button
          btn
          @click="notifyMe"
      >
        {{ t('button.notify-me') }}
      </button>
    </div>
    <div flex justify-center>
      <img src="/preview.png" z-20 rounded-md alt="">
      <img src="/image-7.svg" absolute z-30 left-0 bottom-0  rounded-md class="hidden sm:block w-20 xl:w-40 xl:-ml-35 -mb-10 xl:-mb-10" alt="">
      <img src="/image-8.svg" absolute right-0  z-10 rounded-md class="hidden sm:block w-20 xl:w-30 xl:-mr-25 -mt-20 xl:-mt-15" alt="">
    </div>
  </div>
</template>

<route lang="yaml">
meta:
layout: default
</route>
