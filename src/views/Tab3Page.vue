<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 3</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
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
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import ExploreContainer from '@/components/ExploreContainer.vue';

const tweets = [
  {
    user: {
      created_at: "2011-09-14T16:22:38.000Z",
      default_profile_image: false,
      description: "Where the 🌎 charts, chats and trades markets",
      fast_followers_count: 0,
      favourites_count: 19294,
      followers_count: 660776,
      friends_count: 4166,
      has_custom_timelines: false,
      is_translator: false,
      listed_count: 4257,
      location: "New York, USA",
      media_count: 2448,
      name: "TradingView",
      normal_followers_count: 660776,
      possibly_sensitive: false,
      profile_banner_url:
        "https://pbs.twimg.com/profile_banners/373457750/1669906179",
      profile_image_url_https:
        "https://pbs.twimg.com/profile_images/1598328471729704963/D7slFVZN_normal.jpg",
      screen_name: "tradingview",
      statuses_count: 153038,
      translator_type: "none",
      url: "https://t.co/2qxxDllrOt",
      verified: false,
      withheld_in_countries: [],
      id_str: "373457750",
    },
    id: "1659280339716526081",
    conversation_id: "1659280339716526081",
    full_text: "NVIDIA. That's the tweet. https://t.co/jsYAxlHrpU",
    reply_count: 44,
    retweet_count: 102,
    favorite_count: 734,
    hashtags: [],
    symbols: [],
    user_mentions: [],
    urls: [],
    media: [
      {
        media_url: "https://pbs.twimg.com/media/FwbyoviX0AEHnVK.jpg",
        type: "photo",
      },
    ],
    url: "https://twitter.com/tradingview/status/1659280339716526081",
    created_at: "2023-05-18T19:30:35.000Z",
    view_count: 68130,
    quote_count: 11,
    is_quote_tweet: false,
    is_retweet: false,
    is_truncated: false,
    startUrl: "https://twitter.com/tradingview",
  },
  {
    user: {
      created_at: "2011-09-14T16:22:38.000Z",
      default_profile_image: false,
      description: "Where the 🌎 charts, chats and trades markets",
      fast_followers_count: 0,
      favourites_count: 19294,
      followers_count: 660776,
      friends_count: 4166,
      has_custom_timelines: false,
      is_translator: false,
      listed_count: 4257,
      location: "New York, USA",
      media_count: 2448,
      name: "TradingView",
      normal_followers_count: 660776,
      possibly_sensitive: false,
      profile_banner_url:
        "https://pbs.twimg.com/profile_banners/373457750/1669906179",
      profile_image_url_https:
        "https://pbs.twimg.com/profile_images/1598328471729704963/D7slFVZN_normal.jpg",
      screen_name: "tradingview",
      statuses_count: 153038,
      translator_type: "none",
      url: "https://t.co/2qxxDllrOt",
      verified: false,
      withheld_in_countries: [],
      id_str: "373457750",
    },
    id: "1659246410292658189",
    conversation_id: "1659246247062958081",
    full_text:
      "@binance Want more details about this exciting release?\n\nRead our launch post: https://t.co/JBLhWvP5By",
    reply_count: 8,
    retweet_count: 4,
    favorite_count: 62,
    hashtags: [],
    symbols: [],
    user_mentions: [
      {
        id_str: "877807935493033984",
        name: "Binance",
        screen_name: "binance",
        profile: "https://twitter.com/binance",
      },
    ],
    urls: [
      {
        url: "https://t.co/JBLhWvP5By",
        expanded_url:
          "https://www.tradingview.com/blog/en/binance-spot-trading-on-tradingview-38297/",
        display_url: "tradingview.com/blog/en/binanc…",
      },
    ],
    media: [],
    url: "https://twitter.com/tradingview/status/1659246410292658189",
    created_at: "2023-05-18T17:15:46.000Z",
    view_count: 15262,
    quote_count: 0,
    is_quote_tweet: false,
    is_retweet: false,
    is_truncated: false,
    startUrl: "https://twitter.com/tradingview",
  },
  {
    user: {
      created_at: "2011-09-14T16:22:38.000Z",
      default_profile_image: false,
      description: "Where the 🌎 charts, chats and trades markets",
      fast_followers_count: 0,
      favourites_count: 19294,
      followers_count: 660776,
      friends_count: 4166,
      has_custom_timelines: false,
      is_translator: false,
      listed_count: 4257,
      location: "New York, USA",
      media_count: 2448,
      name: "TradingView",
      normal_followers_count: 660776,
      possibly_sensitive: false,
      profile_banner_url:
        "https://pbs.twimg.com/profile_banners/373457750/1669906179",
      profile_image_url_https:
        "https://pbs.twimg.com/profile_images/1598328471729704963/D7slFVZN_normal.jpg",
      screen_name: "tradingview",
      statuses_count: 153038,
      translator_type: "none",
      url: "https://t.co/2qxxDllrOt",
      verified: false,
      withheld_in_countries: [],
      id_str: "373457750",
    },
    id: "1659246247062958081",
    conversation_id: "1659246247062958081",
    full_text:
      "We have exciting news to share... 🤩🤩\n\nDrum roll please… 🥁🥁\n\n@binance brings its Spot trading to TradingView!\n\nWith this latest integration, we now support 350 tokens via Binance directly. Connect your Binance account with TradingView to plan and execute with precision.",
    reply_count: 43,
    retweet_count: 66,
    favorite_count: 452,
    hashtags: [],
    symbols: [],
    user_mentions: [
      {
        id_str: "877807935493033984",
        name: "Binance",
        screen_name: "binance",
        profile: "https://twitter.com/binance",
      },
    ],
    urls: [],
    media: [],
    url: "https://twitter.com/tradingview/status/1659246247062958081",
    created_at: "2023-05-18T17:15:07.000Z",
    view_count: 58006,
    quote_count: 11,
    is_quote_tweet: false,
    is_retweet: false,
    is_truncated: false,
    startUrl: "https://twitter.com/tradingview",
  },
  {
    user: {
      created_at: "2011-09-14T16:22:38.000Z",
      default_profile_image: false,
      description: "Where the 🌎 charts, chats and trades markets",
      fast_followers_count: 0,
      favourites_count: 19294,
      followers_count: 660776,
      friends_count: 4166,
      has_custom_timelines: false,
      is_translator: false,
      listed_count: 4257,
      location: "New York, USA",
      media_count: 2448,
      name: "TradingView",
      normal_followers_count: 660776,
      possibly_sensitive: false,
      profile_banner_url:
        "https://pbs.twimg.com/profile_banners/373457750/1669906179",
      profile_image_url_https:
        "https://pbs.twimg.com/profile_images/1598328471729704963/D7slFVZN_normal.jpg",
      screen_name: "tradingview",
      statuses_count: 153038,
      translator_type: "none",
      url: "https://t.co/2qxxDllrOt",
      verified: false,
      withheld_in_countries: [],
      id_str: "373457750",
    },
    id: "1659176863103610880",
    conversation_id: "1659176863103610880",
    full_text:
      "We're pleased to welcome @infoyatirim to our platform! 🎉\n\nTraders in Turkey can now connect their brokerage to their favorite charting platform. 🤝\n\nChart, plan, and execute: https://t.co/0HOSAID3Ax",
    reply_count: 11,
    retweet_count: 11,
    favorite_count: 69,
    hashtags: [],
    symbols: [],
    user_mentions: [
      {
        id_str: "2597991817",
        name: "İnfo Yatırım Menkul Değerler",
        screen_name: "infoyatirim",
        profile: "https://twitter.com/infoyatirim",
      },
    ],
    urls: [
      {
        url: "https://t.co/0HOSAID3Ax",
        expanded_url: "https://www.tradingview.com/broker/infoyatirim/",
        display_url: "tradingview.com/broker/infoyat…",
      },
    ],
    media: [],
    url: "https://twitter.com/tradingview/status/1659176863103610880",
    created_at: "2023-05-18T12:39:24.000Z",
    view_count: 24714,
    quote_count: 1,
    is_quote_tweet: false,
    is_retweet: false,
    is_truncated: false,
    startUrl: "https://twitter.com/tradingview",
  },
  {
    user: {
      created_at: "2011-09-14T16:22:38.000Z",
      default_profile_image: false,
      description: "Where the 🌎 charts, chats and trades markets",
      fast_followers_count: 0,
      favourites_count: 19294,
      followers_count: 660776,
      friends_count: 4166,
      has_custom_timelines: false,
      is_translator: false,
      listed_count: 4257,
      location: "New York, USA",
      media_count: 2448,
      name: "TradingView",
      normal_followers_count: 660776,
      possibly_sensitive: false,
      profile_banner_url:
        "https://pbs.twimg.com/profile_banners/373457750/1669906179",
      profile_image_url_https:
        "https://pbs.twimg.com/profile_images/1598328471729704963/D7slFVZN_normal.jpg",
      screen_name: "tradingview",
      statuses_count: 153038,
      translator_type: "none",
      url: "https://t.co/2qxxDllrOt",
      verified: false,
      withheld_in_countries: [],
      id_str: "373457750",
    },
    id: "1658865798344056832",
    conversation_id: "1658865798344056832",
    full_text: "Money market funds 🤯 https://t.co/G9l8nwiCnx",
    reply_count: 29,
    retweet_count: 64,
    favorite_count: 451,
    hashtags: [],
    symbols: [],
    user_mentions: [],
    urls: [],
    media: [
      {
        media_url: "https://pbs.twimg.com/media/FwV5oE2WAAI3-z3.jpg",
        type: "photo",
      },
    ],
    url: "https://twitter.com/tradingview/status/1658865798344056832",
    created_at: "2023-05-17T16:03:21.000Z",
    view_count: 53616,
    quote_count: 8,
    is_quote_tweet: false,
    is_retweet: false,
    is_truncated: false,
    startUrl: "https://twitter.com/tradingview",
  },
  {
    user: {
      created_at: "2011-09-14T16:22:38.000Z",
      default_profile_image: false,
      description: "Where the 🌎 charts, chats and trades markets",
      fast_followers_count: 0,
      favourites_count: 19294,
      followers_count: 660776,
      friends_count: 4166,
      has_custom_timelines: false,
      is_translator: false,
      listed_count: 4257,
      location: "New York, USA",
      media_count: 2448,
      name: "TradingView",
      normal_followers_count: 660776,
      possibly_sensitive: false,
      profile_banner_url:
        "https://pbs.twimg.com/profile_banners/373457750/1669906179",
      profile_image_url_https:
        "https://pbs.twimg.com/profile_images/1598328471729704963/D7slFVZN_normal.jpg",
      screen_name: "tradingview",
      statuses_count: 153038,
      translator_type: "none",
      url: "https://t.co/2qxxDllrOt",
      verified: false,
      withheld_in_countries: [],
      id_str: "373457750",
    },
    id: "1658534960653819908",
    conversation_id: "1658534960653819908",
    full_text:
      "NVIDIA market cap on January 1st: $350 billion\n\nToday: $730 billion\n\nThat's an increase of $380 billion in under six months. https://t.co/b4FBhXVnbg",
    reply_count: 44,
    retweet_count: 63,
    favorite_count: 419,
    hashtags: [],
    symbols: [],
    user_mentions: [],
    urls: [],
    media: [
      {
        media_url: "https://pbs.twimg.com/media/FwRMDXVWYAI0m0M.jpg",
        type: "photo",
      },
    ],
    url: "https://twitter.com/tradingview/status/1658534960653819908",
    created_at: "2023-05-16T18:08:43.000Z",
    view_count: 49040,
    quote_count: 18,
    is_quote_tweet: false,
    is_retweet: false,
    is_truncated: false,
    startUrl: "https://twitter.com/tradingview",
  },
  {
    user: {
      created_at: "2011-09-14T16:22:38.000Z",
      default_profile_image: false,
      description: "Where the 🌎 charts, chats and trades markets",
      fast_followers_count: 0,
      favourites_count: 19294,
      followers_count: 660776,
      friends_count: 4166,
      has_custom_timelines: false,
      is_translator: false,
      listed_count: 4257,
      location: "New York, USA",
      media_count: 2448,
      name: "TradingView",
      normal_followers_count: 660776,
      possibly_sensitive: false,
      profile_banner_url:
        "https://pbs.twimg.com/profile_banners/373457750/1669906179",
      profile_image_url_https:
        "https://pbs.twimg.com/profile_images/1598328471729704963/D7slFVZN_normal.jpg",
      screen_name: "tradingview",
      statuses_count: 153038,
      translator_type: "none",
      url: "https://t.co/2qxxDllrOt",
      verified: false,
      withheld_in_countries: [],
      id_str: "373457750",
    },
    id: "1658513728428441616",
    conversation_id: "1658513728428441616",
    full_text: "Think before you trade.",
    reply_count: 54,
    retweet_count: 104,
    favorite_count: 546,
    hashtags: [],
    symbols: [],
    user_mentions: [],
    urls: [],
    media: [],
    url: "https://twitter.com/tradingview/status/1658513728428441616",
    created_at: "2023-05-16T16:44:21.000Z",
    view_count: 48097,
    quote_count: 18,
    is_quote_tweet: false,
    is_retweet: false,
    is_truncated: false,
    startUrl: "https://twitter.com/tradingview",
  },
  {
    user: {
      created_at: "2011-09-14T16:22:38.000Z",
      default_profile_image: false,
      description: "Where the 🌎 charts, chats and trades markets",
      fast_followers_count: 0,
      favourites_count: 19294,
      followers_count: 660776,
      friends_count: 4166,
      has_custom_timelines: false,
      is_translator: false,
      listed_count: 4257,
      location: "New York, USA",
      media_count: 2448,
      name: "TradingView",
      normal_followers_count: 660776,
      possibly_sensitive: false,
      profile_banner_url:
        "https://pbs.twimg.com/profile_banners/373457750/1669906179",
      profile_image_url_https:
        "https://pbs.twimg.com/profile_images/1598328471729704963/D7slFVZN_normal.jpg",
      screen_name: "tradingview",
      statuses_count: 153038,
      translator_type: "none",
      url: "https://t.co/2qxxDllrOt",
      verified: false,
      withheld_in_countries: [],
      id_str: "373457750",
    },
    id: "1658266284675547136",
    conversation_id: "1658266284675547136",
    full_text:
      "This chart of gold will make you think. https://t.co/aGStG7vDhA",
    reply_count: 127,
    retweet_count: 105,
    favorite_count: 838,
    hashtags: [],
    symbols: [],
    user_mentions: [],
    urls: [],
    media: [
      {
        media_url: "https://pbs.twimg.com/media/FwNYE5OXsAEbOmr.jpg",
        type: "photo",
      },
    ],
    url: "https://twitter.com/tradingview/status/1658266284675547136",
    created_at: "2023-05-16T00:21:06.000Z",
    view_count: 171668,
    quote_count: 27,
    is_quote_tweet: false,
    is_retweet: false,
    is_truncated: false,
    startUrl: "https://twitter.com/tradingview",
  },
  {
    user: {
      created_at: "2011-09-14T16:22:38.000Z",
      default_profile_image: false,
      description: "Where the 🌎 charts, chats and trades markets",
      fast_followers_count: 0,
      favourites_count: 19294,
      followers_count: 660776,
      friends_count: 4166,
      has_custom_timelines: false,
      is_translator: false,
      listed_count: 4257,
      location: "New York, USA",
      media_count: 2448,
      name: "TradingView",
      normal_followers_count: 660776,
      possibly_sensitive: false,
      profile_banner_url:
        "https://pbs.twimg.com/profile_banners/373457750/1669906179",
      profile_image_url_https:
        "https://pbs.twimg.com/profile_images/1598328471729704963/D7slFVZN_normal.jpg",
      screen_name: "tradingview",
      statuses_count: 153038,
      translator_type: "none",
      url: "https://t.co/2qxxDllrOt",
      verified: false,
      withheld_in_countries: [],
      id_str: "373457750",
    },
    id: "1658229474251423746",
    conversation_id: "1658229418676846595",
    full_text: "Check this out: https://t.co/EBa74drqey",
    reply_count: 3,
    retweet_count: 2,
    favorite_count: 20,
    hashtags: [],
    symbols: [],
    user_mentions: [],
    urls: [
      {
        url: "https://t.co/EBa74drqey",
        expanded_url:
          "https://www.tradingview.com/symbols/NASDAQ-TSLA/financials-revenue/",
        display_url: "tradingview.com/symbols/NASDAQ…",
      },
    ],
    media: [],
    url: "https://twitter.com/tradingview/status/1658229474251423746",
    created_at: "2023-05-15T21:54:49.000Z",
    view_count: 19280,
    quote_count: 1,
    is_quote_tweet: false,
    is_retweet: false,
    is_truncated: false,
    startUrl: "https://twitter.com/tradingview",
  },
  {
    user: {
      created_at: "2011-09-14T16:22:38.000Z",
      default_profile_image: false,
      description: "Where the 🌎 charts, chats and trades markets",
      fast_followers_count: 0,
      favourites_count: 19294,
      followers_count: 660776,
      friends_count: 4166,
      has_custom_timelines: false,
      is_translator: false,
      listed_count: 4257,
      location: "New York, USA",
      media_count: 2448,
      name: "TradingView",
      normal_followers_count: 660776,
      possibly_sensitive: false,
      profile_banner_url:
        "https://pbs.twimg.com/profile_banners/373457750/1669906179",
      profile_image_url_https:
        "https://pbs.twimg.com/profile_images/1598328471729704963/D7slFVZN_normal.jpg",
      screen_name: "tradingview",
      statuses_count: 153038,
      translator_type: "none",
      url: "https://t.co/2qxxDllrOt",
      verified: false,
      withheld_in_countries: [],
      id_str: "373457750",
    },
    id: "1658229418676846595",
    conversation_id: "1658229418676846595",
    full_text:
      "Tesla revenue by energy generation and storage \n\n2016 - $181 million\n2017 - $1.12B\n2018 - $1.56B\n2019 - $1.53B\n2020 - $1.99B\n2021 - $2.79B \n2022 - $3.91B ‼️\n\n$TSLA",
    reply_count: 8,
    retweet_count: 22,
    favorite_count: 160,
    hashtags: [],
    symbols: ["TSLA"],
    user_mentions: [],
    urls: [],
    media: [],
    url: "https://twitter.com/tradingview/status/1658229418676846595",
    created_at: "2023-05-15T21:54:36.000Z",
    view_count: 30607,
    quote_count: 2,
    is_quote_tweet: false,
    is_retweet: false,
    is_truncated: false,
    startUrl: "https://twitter.com/tradingview",
  },
];

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
