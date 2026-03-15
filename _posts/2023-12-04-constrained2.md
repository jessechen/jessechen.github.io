---
layout: post
title: Constrained programming, part 2
date: 2023-12-04
categories: programming
---
The second letter in "etaoin shrdlu" is t. Some Ruby method names and keywords that contain the letter t include return, #match, true, #split, #to_i, next, #empty?, #length, and #select. I write this here so I don't have to figure out how to talk around those explicitly forbidden words.

Of the above, I couldn't figure out how to get around #to_i without implementing it myself.

<hr>
## Day 2 | Ruby | Avoiding glyph before 'u'
<pre>
def as_number(word)
    if word == "100"
        100
    elsif word.size == 1
        word.ord - 48
    else
        (word.ord - 48) * 10 + word.chars[1].ord - 48
    end
end

# Problem 1
games = IO.readlines('02').map(&:chop)
ids = games.map do |game|
    draws = game.scan /(\d+) ([bgr])/
    invalid = draws.keep_if do |draw|
        num = as_number(draw[0])
        color = draw[1]
        (num > 12 && color == 'r') || (num > 13 && color == 'g') || (num > 14 && color == 'b')
    end
    invalid.size == 0 ? as_number(game.scan(/Game (\d+)/)[0][0]) : 0
end

p ids.sum

# Problem 2
powers = games.map do |game|
    cubes = {"r" => 0, "b" => 0, "g" => 0}
    game.scan(/(\d+) ([bgr])/) do |draw|
        num = as_number(draw[0])
        color = draw[1]
        cubes[color] = num if cubes[color] < num
    end
    cubes.values.reduce(&:*)
end

p powers.sum
</pre>
