---
name: proveny-video
description: Make or remix a short video ad of the user's product with the Proveny MCP tools. Use when the user asks for a product video, a video ad, a UGC ad, or a remix of their Proveny footage.
---

# Make a video ad with Proveny

The Proveny MCP server (`proveny`) reads the product, prices and renders. You talk with the user and
write the script.

1. Ask who the seller sells to before you start.
2. `create_video` from the product link or a `productId` from `list_products`. A new link costs
   `analyzeCredits` (see `get_credit_balance`): show the price and ask first. An existing product
   costs nothing.
3. Read `get_video` until the sell angles are ready. Show them and work on **one sell angle at a
   time**: its Persona, Angle and Value.
4. After the user picks the angle, ask the length: 15 or 30 seconds (`set_video_options`). Do this
   before you write the script.
5. Write the script with `update_script` and show it to the user.
6. `quote_render`, show the price in Credits and the balance, and wait for the user's yes. Then
   `render_video` with exactly the quoted credits.
7. Renders take a few minutes. Keep reading `get_video` until the status is done, then tell the user
   the video is ready and give the link.

Remix: `list_footage`, `propose_remix_plan`, show the price, wait for the yes, `start_remix`, then
read `get_remix` until it is done.

Rules:

- Never spend credits without the user's yes to that exact price: a new product read, a render or a
  remix.
- When credits run short, give the user the `topupUrl`. Do not retry until the user says they topped
  up.
