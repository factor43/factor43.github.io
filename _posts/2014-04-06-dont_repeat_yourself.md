---
layout: post
author: sjl
title: Don’t repeat yourself (DRY)
---
*“Every piece of knowledge must have a single, unambiguous, authoritative representation within a system.”*

After a few years of practice, some software development principles become so ingrained and automatic that you forget that they are actually principles at all. Or that the principle has a fancy name and a wikipedia entry.

Someone posted a code snippet recently that wasn’t behaving as they expected. Curious, I had a quick look and spotted a potential problem right away – their “entity” class had two representations of it’s own position – an explicit member variable and the transform within a visual model. The code controlling the entities behavior was interchangeably using one or the other, leading to them becoming out of sync and resulting in the unexpected behavior.

Of course, sometimes there may be a good reason to duplicate a member variable or other piece of data (e.g. caching for performance reasons), but usually a single unambiguous representation just seems like the obvious way to do things. Anything else leads to unnecessary complexity and hence bugs.

So the very next day I’m at the pharmacy (getting some pre-travel medication). I hand over my Medicare card, make the purchase and get an invoice. But I notice something odd – the address on the invoice is really out of date. It’s the place I lived before even the previous place – 5 years ago at least. So I ask the pharmacist how this could be – after all, Medicare have my current address and I gave you my Medicare card. Oh it’s simple he says – the first time you came in (i.e. 5 years ago), our system takes a copy of your details from Medicare, and now that is out of date. I briefly considered giving the pharmacist a short lesson about the DRY software engineering principle but decided to just get the information re-synced/corrected and be on my way.
