---
title: Notion Progress Bars
updated: 2022-01-11 15:25:36Z
created: 2022-01-04 07:56:05Z
author: André Luz
tags:
  - misc
---

if(prop("Percent Done") >= 1, "■■■■■■■■■■" + format(round(prop("Percent Done") * 100)) + "%", slice("■■■■■■■■■■", 0, round(prop("Percent Done") * 10)) + slice("**☐☐☐☐☐☐☐☐☐☐**", 0, round((.999 - prop("Percent Done")) * 10)) + " " + if(prop("Percent Done") == 0, "0", format(round(prop("Percent Done") * 100))) + "%")

if(prop("Percent Done") >= 1, "▓▓▓▓▓▓▓▓▓▓ " + format(round(prop("Percent Done") * 100)) + "%", slice("▓▓▓▓▓▓▓▓▓▓", 0, round(prop("Percent Done") * 10)) + slice("░░░░░░░░░░", 0, round((.999 - prop("Percent Done")) * 10)) + " " + if(prop("Percent Done") == 0, "0", format(round(prop("Percent Done") * 100))) + "%")

if(prop("Percent Done") >= 1, "◆◆◆◆◆◆◆◆◆◆" + format(round(prop("Percent Done") * 100)) + "%", slice("◆◆◆◆◆◆◆◆◆◆", 0, round(prop("Percent Done") * 10)) + slice("◇◇◇◇◇◇◇◇◇◇", 0, round((.999 - prop("Percent Done")) * 10)) + " " + if(prop("Percent Done") == 0, "0", format(round(prop("Percent Done") * 100))) + "%")

if(prop("Percent Done") >= 1, "★★★★★★★★★★" + format(round(prop("Percent Done") * 100)) + "%", slice("★★★★★★★★★★", 0, round(prop("Percent Done") * 10)) + slice("☆☆☆☆☆☆☆☆☆☆", 0, round((.999 - prop("Percent Done")) * 10)) + " " + if(prop("Percent Done") == 0, "0", format(round(prop("Percent Done") * 100))) + "%")

if(prop("Percent Done") >= 1, "▮▮▮▮▮▮▮▮▮▮" + format(round(prop("Percent Done") * 100)) + "%", slice("▮▮▮▮▮▮▮▮▮▮", 0, round(prop("Percent Done") * 10)) + slice("▯▯▯▯▯▯▯▯▯▯", 0, round((.999 - prop("Percent Done")) * 10)) + " " + if(prop("Percent Done") == 0, "0", format(round(prop("Percent Done") * 100))) + "%")

if(prop("Percent Done") >= 1, "■■■■■■■■■■" + format(round(prop("Percent Done") * 100)) + "%", slice("■■■■■■■■■■", 0, round(prop("Percent Done") * 10)) + slice("❒❒❒❒❒❒❒❒❒❒", 0, round((.999 - prop("Percent Done")) * 10)) + " " + if(prop("Percent Done") == 0, "0", format(round(prop("Percent Done") * 100))) + "%")

if(prop("Percent Done") >= 1, "◼◼◼◼◼◼◼◼◼◼" + format(round(prop("Percent Done") * 100)) + "%", slice("◼◼◼◼◼◼◼◼◼◼", 0, round(prop("Percent Done") * 10)) + slice("◻◻◻◻◻◻◻◻◻◻", 0, round((.999 - prop("Percent Done")) * 10)) + " " + if(prop("Percent Done") == 0, "0", format(round(prop("Percent Done") * 100))) + "%")