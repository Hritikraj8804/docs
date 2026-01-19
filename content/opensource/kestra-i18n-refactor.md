---
title: "Refactor SurveyDialog i18n translations"
date: 2025-11-17
project: "Kestra"
repo: "kestra-io/kestra"
prNumber: "12985"
prLink: "https://github.com/kestra-io/kestra/pull/12985"
status: "merged"
tags: ["Vue.js", "i18n", "Frontend"]
description: "Refactored SurveyDialog.vue to use globally available $t helper instead of useI18n composable"
---

Refactored `SurveyDialog.vue` to remove the unnecessary `useI18n` composable and use the globally available `$t` helper in the template.

This aligns the component with Kestra's standard i18n usage and simplifies translation handling.
