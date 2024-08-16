---
layout: post
title: "Intro to _richDevs"
date: 2024-08-16
---

<!-- ## Header -->

![Screenshot 2024-08-16 at 12 14 09 AM](https://github.com/user-attachments/assets/25cf3f5b-03e8-4b5e-9c84-4b6ab5787667)

<a href="https://jolly-cherry-f189.richieabenoja25.workers.dev">Link to minnow color combo generator</a>

<b>Refresh the page to generate new images.</b>

## Building the Minnow Color Generator
I’ve always enjoyed tech, but like many of us, I sometimes struggle to keep my momentum going when it comes to personal projects. After a long day of coding at work, it’s easy to let my own ideas fall by the wayside. I realized I needed something to keep me engaged—a project that not only challenges me but also allows me to blend my interests. That’s how the minnow color generator came to be.

## Why I’m Starting This Blog
Before diving into the technical details, I want to share why I’ve decided to start this blog. For a while now, I’ve been looking for ways to stay committed to my personal growth in tech. I’ve found that sharing my progress publicly helps keep me motivated. It adds a level of accountability and gives me a reason to push through those moments when I might otherwise put things off.

This blog is my way of documenting that journey. I hope it will be a place where I can not only share what I’m working on but also connect with others who might be on a similar path, whether you’re interested in tech, bait making, or just looking for some inspiration to keep going with your own projects.

Give my baitmaking/fishing instagram <a href="https://www.instagram.com/richjigs/">RichJigs</a> a look if you're curious!


## The Minnow Color Generator Inspiration
With my company’s Cloudflare AI Hacknight event just around the corner, I couldn’t resist getting a sneak peek at the cool tech we’ll be diving into. I discovered they have some text-to-image models available for free, so I figured, why not have a little fun? I decided to play around with them to see if I could come up with some awesome jig color combinations for inspiration on future projects.

## Technical Breakdown
### Step 1: <a href="https://dash.cloudflare.com/sign-up">Sign Up for CloudFlare Account</a>
### Step 2: Navigate to the Workers & Pages Section
<img width="256" alt="Screenshot 2024-08-16 at 12 41 59 AM" src="https://github.com/user-attachments/assets/f6d778a9-d244-42bf-9c8b-102015d07cfe">

### Step 3: Create your First Workers Project

### Step 4: Navigate to the Edit Code button in the top right
<img width="927" alt="Screenshot 2024-08-16 at 12 57 54 AM" src="https://github.com/user-attachments/assets/f1d676c3-e3b0-4456-bdae-1a8f5b115915">

![Screenshot 2024-08-16 at 12 59 11 AM](https://github.com/user-attachments/assets/f4872998-3744-4131-aa3e-ef2309b749fc)

### Step 5: Here's the Code and Prompt I Used

```
export default {
  async fetch(request, env) {

    const inputs = {
      prompt: "A realistic image of five 2.25-inch soft plastic fishing lures shaped like minnows, with a clear emphasis on a dual color scheme. Each lure should have a distinctly colored top and a contrasting belly, using any combination of colors across the spectrum. The lures should include realistic details like small fins, a pointed head, and a subtle glitter overlay in a complementary color. The contrasting colors should be bold and clearly separated, highlighting the difference between the top and bottom. The lures should be shown against a plain, light background, with attention to the texture and reflective qualities of the plastic and glitter."
    };

  const response = await env.AI.run(
      "@cf/stabilityai/stable-diffusion-xl-base-1.0",
      inputs
    );

    return new Response(response, {
      headers: {
        'content-type': 'image/png',
      },
    });
  },
};

```

### Step 6: <a href="https://developers.cloudflare.com/workers-ai/models/">CloudFlare Workers AI Models</a>

You can play around with the different models here to create whatever you like. There are implementation examples for each of the models.
