---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: true

description: ....
thumbnail: "/images/{{ replace .Name "-" " " | title }}.png"
image: "/images/{{ replace .Name "-" " " | title }}.png"
---

