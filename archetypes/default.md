---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: false
menu:
  sidebar:
    name: {{ replace .Name "-" " " | title }}
    identifier: {{ .Name | title }}
    parent: <section>-news
    weight: 10
---

