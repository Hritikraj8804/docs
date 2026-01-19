---
title: "Migrate Toc.vue to Vue 3 Composition API with TypeScript"
date: 2025-11-24
project: "Kestra"
repo: "kestra-io/kestra"
prNumber: "13113"
prLink: "https://github.com/kestra-io/kestra/pull/13113"
status: "merged"
tags: ["Vue.js", "TypeScript", "Frontend"]
description: "Migrated Toc.vue component from Vue 2 Options API to Vue 3 Composition API with full TypeScript support"
---

Migrated the `ui/src/components/plugins/Toc.vue` component from the Vue 2 Options API (JavaScript) to the Vue 3 Composition API using `<script setup lang="ts">`.

Changes include:
- Converting data, computed properties, methods, and watchers to Composition API (`ref`, `computed`, `watch`, `nextTick`)
- Using `defineProps` and `defineEmits` with full TypeScript generics
- Adding explicit interfaces for `Plugin` and `PluginElement`
- Retaining the existing template and behavior with no UI or functional changes
