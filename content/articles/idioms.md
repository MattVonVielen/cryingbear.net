---
title: "Idiomatic Code: a flawed justification"
date: 2022-05-11T15:57:28-06:00
draft: true
---

Idioms develop for reasons, and the oldest idioms in a language are usually a function of the original intended problems which that language was tooled for. Languages tooled for systems programming (writing servers and OS components) have a value set which aligns with the intended problem space, and systems programming's problem space doesn't overlap much at all with the problem space of highly maintainable business software (i.e. CRUD apps). 
	
Idiomatic Go values horizontal terseness highly - ideal variable names are one or two characters at most, resulting in code that reads similarly to algebraic expressions in pure math. While this may be well suited to the mental modelling of folks who think in algebraic expressions, it is far less so to verbal thinkers. I myself am very much a verbal thinker, and while I don't know of any concrete data indicating what the likely proportions of thinking-types are within the broader software industry, my uneducated guess would be that fewer than 30% of us are capable of thinking in abstract algebra without some serious effort.