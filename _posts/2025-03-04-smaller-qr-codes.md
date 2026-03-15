---
layout: post
title: Smaller QR codes for URLs
date: 2025-03-04
categories: misc
---
For historical reasons, QR codes have four different encodings they use depending on the characters they need to represent. Purely numeric codes use the most efficient encoding, then alphanumeric, then binary, then kanji (*historical reasons*). The thing is, "alphanumeric" here only includes capital letters, not lowercase letters. [Specifically, it's 0-9, A-Z, space, and $%*+-./:](https://en.wikipedia.org/wiki/QR_code#Information_capacity) which is enough to encode a url AS LONG AS YOU ONLY USE UPPERCASE.

If your url includes lowercase letters, it'll fall through and get encoded as binary (Latin-1) instead, which is significantly longer, leading to a larger QR code.

(h/t [Why are QR Codes with capital letters smaller than QR codes with lower-case letters?](https://shkspr.mobi/blog/2025/02/why-are-qr-codes-with-capital-letters-smaller-than-qr-codes-with-lower-case-letters/) )
