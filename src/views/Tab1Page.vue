import axios from 'axios';

<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 1</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <!-- <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 1</ion-title>
          
        </ion-toolbar>
      </ion-header>

      <ExploreContainer name="Hello World" /> -->
      <div v-if="!tweets">Loading...</div>
      <pre v-else>{{ tweets }}</pre>
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
</script>
