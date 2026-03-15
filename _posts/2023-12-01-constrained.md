---
layout: post
title: Constrained programming
date: 2023-12-01
categories: programming
---
I've enjoyed constrained writing (e.g. [Oulipo](https://en.wikipedia.org/wiki/Oulipo)) for a long time and am going to be trying to practice constrained programming in Advent of Code for as long as I can maintain interest this year. In particular, my plan is to go through each day as a [lipogram](https://en.wikipedia.org/wiki/Lipogram) of the nth-most-frequent letter in English. For the first twelve, even though English [letter frequency](https://en.wikipedia.org/wiki/Letter_frequency) is slightly different than [ETAOIN SHRDLU](https://en.wikipedia.org/wiki/Etaoin_shrdlu), I'll use that iconic order.

So my day 1 solution will not include the letter 'e', day 2 will not include the letter 't', and so on. I'm excited to try this out. Here's day 1:

<hr>
## Day 1 | Ruby | Avoiding fifth glyph
<pre>
# part 1
digits = inputs.map { |input| input.gsub(/\D/, '')}
calibrations = digits.map { |digit| digit.chars.first.to_i * 10 + digit.chars.last.to_i }
p calibrations.sum

# part 2
glyph_to_avoid = "d".succ
@trigrams = {"two" => 2, "six" => 6}
@trigrams["onz".gsub(/z/, glyph_to_avoid)] = 1
@quadragrams = {"four" => 4}
@quadragrams["fivz".gsub(/z/, glyph_to_avoid)] = 5
@quadragrams["ninz".gsub(/z/, glyph_to_avoid)] = 9
@quintagrams = {}
@quintagrams["thrzz".gsub(/z/, glyph_to_avoid)] = 3
@quintagrams["szvzn".gsub(/z/, glyph_to_avoid)] = 7
@quintagrams["zight".gsub(/z/, glyph_to_avoid)] = 8

calibrations = inputs.map { |input|
    first_digit = nil
    (0..input.chars.count - 1).map { |idx|
        first_digit = input[idx].to_i if !first_digit && /\d/ =~ input[idx]
        tri = input[idx-2, 3] if idx >= 2
        first_digit = @trigrams[tri] if !first_digit && tri && @trigrams[tri]
        quad = input[idx-3, 4] if idx >= 3
        first_digit = @quadragrams[quad] if !first_digit && quad && @quadragrams[quad]
        quint = input[idx-4, 5] if idx >= 4
        first_digit = @quintagrams[quint] if !first_digit && quint && @quintagrams[quint]
    }
    last_digit = nil
    (1..input.chars.count).map { |idx|
        last_digit = input[-idx].to_i if !last_digit && /\d/ =~ input[-idx]
        tri = input[-idx, 3] if idx >= 2
        last_digit = @trigrams[tri] if !last_digit && tri && @trigrams[tri]
        quad = input[-idx, 4] if idx >= 3
        last_digit = @quadragrams[quad] if !last_digit && quad && @quadragrams[quad]
        quint = input[-idx, 5] if idx >= 4
        last_digit = @quintagrams[quint] if !last_digit && quint && @quintagrams[quint]
    }
    first_digit * 10 + last_digit
}
p calibrations.sum
</pre>
Not using control flow words was tough to work around. I initially had 'x' for a proxy glyph until I got to 'six'.
