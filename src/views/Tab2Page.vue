import axios from 'axios';

<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 2</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <!-- <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 2</ion-title>
        </ion-toolbar>
      </ion-header>

      <ExploreContainer name="Tab 2 page" /> -->
      <div v-if="!tweets">Loading...</div>
      <pre v-else>
        <div class="flex flex-col gap-4 px-4 pt-2 pb-4">
        <div v-for="tweet in tweets">
          <div class="max-w-xl rounded-xl border border-gray-200 bg-white p-4 dark:border-gray-700 dark:bg-gray-800">
            <div class="flex justify-between">
              <div class="flex items-center">
                <img class="h-11 w-11 rounded-full" :src="tweet.user.profile_image_url_https" />
                <div class="ml-1.5 text-sm leading-tight">
                  <span class="block font-bold text-black dark:text-gray-200">
                    {{ tweet.user.name }}</span>
                  <span class="block font-normal text-gray-500 dark:text-gray-400">
                    @{{ tweet.user.screen_name }}</span>
                </div>
              </div>
              <a :href="tweet.url" target="_blank">
                <svg class="inline-block h-6 w-auto fill-current text-blue-400" viewBox="0 0 24 24">
                  <g>
                    <path
                      d="M23.643 4.937c-.835.37-1.732.62-2.675.733.962-.576 1.7-1.49 2.048-2.578-.9.534-1.897.922-2.958 1.13-.85-.904-2.06-1.47-3.4-1.47-2.572 0-4.658 2.086-4.658 4.66 0 .364.042.718.12 1.06-3.873-.195-7.304-2.05-9.602-4.868-.4.69-.63 1.49-.63 2.342 0 1.616.823 3.043 2.072 3.878-.764-.025-1.482-.234-2.11-.583v.06c0 2.257 1.605 4.14 3.737 4.568-.392.106-.803.162-1.227.162-.3 0-.593-.028-.877-.082.593 1.85 2.313 3.198 4.352 3.234-1.595 1.25-3.604 1.995-5.786 1.995-.376 0-.747-.022-1.112-.065 2.062 1.323 4.51 2.093 7.14 2.093 8.57 0 13.255-7.098 13.255-13.254 0-.2-.005-.402-.014-.602.91-.658 1.7-1.477 2.323-2.41z">
                    </path>
                  </g>
                </svg></a>
            </div>
            <p class="mt-3 block text-base leading-snug text-black dark:text-gray-200">
              {{ tweet.full_text }}
            </p>
            <img v-if="tweet.media.length" class="mt-2 rounded-2xl border border-gray-100 dark:border-gray-700"
              :src="tweet.media[0].media_url" />
            <p class="my-0.5 py-1 text-sm text-gray-500 dark:text-gray-400">
              {{ formatDate(tweet.created_at) }}
            </p>
            <div class="my-1 border border-b-0 border-gray-200 dark:border-gray-700"></div>
            <div class="mt-3 flex items-center gap-3 text-gray-900">
              <div class="flex items-center gap-1 text-sm">
                <span class="font-semibold dark:text-gray-200">{{
                  tweet.favorite_count
                }}</span>
                <span class="text-gray-600 dark:text-gray-400">Likes</span>
              </div>
              <div class="flex items-center gap-1 text-sm">
                <span class="font-semibold dark:text-gray-200">{{
                  tweet.reply_count
                }}</span>
                <span class="text-gray-600 dark:text-gray-400">Comment</span>
              </div>
              <div class="flex items-center gap-1 text-sm">
                <span class="font-semibold dark:text-gray-200">{{
                  tweet.retweet_count
                }}</span>
                <span class="text-gray-600 dark:text-gray-400">Retweets</span>
              </div>
            </div>
          </div>
        </div>
      </div>
      </pre>

    </ion-content>

  </ion-page>
</template>

<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import ExploreContainer from '@/components/ExploreContainer.vue';

var tweets: any;


const getTweets = async () => {
  const res = await fetch("https://api.apify.com/v2/acts/quacker~twitter-scraper/runs/last/dataset/items?token=apify_api_gAqIeTLbT7LnVHQtnSZRCNNTTsycN70IaM5f");
  const data = await res.json();
  console.log(data);
  tweets = data;
}

getTweets()

console.log(tweets)

const formatDate = (date: string) => {
  if (!date) return "";

  const formatter = new Intl.DateTimeFormat("en-US", {
    year: "numeric",
    month: "short",
    day: "2-digit",
    hour: "2-digit",
    minute: "2-digit",
  });

  return formatter.format(new Date(date)).replace(/\//g, "-");
};
</script>
