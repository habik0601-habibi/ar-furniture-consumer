# Hearth & Home: a website that uses RoomSense

A fictional furniture store whose website is **plain HTML and CSS**: no React, no build step. It stands in for a real furniture brand's website and shows how a store adds [RoomSense](https://github.com/habik0601-habibi/AR-furniture) (3D, AR, "will it fit?" and delivery cost) to its own pages.

This site is **separate from RoomSense**. RoomSense keeps the 3D models, sizes, finishes, delivery rules, analytics and shopper requests. This site only holds its own text and prices.

## The integration is two lines

```html
<!-- once, at the bottom of the page / in the site template -->
<script src="https://ar-furniture-liard.vercel.app/widget.js" defer></script>

<!-- where the product photos would go -->
<div data-roomsense data-store="hearth" data-product="ravi-coffee-table" data-color="#2f4a3a"></div>
```

Open any page in `products/` and view source to see them. Each product page also has a "How this page uses RoomSense" box with the same lines.

## Deploy

1. In Vercel choose **Add New → Project** and import this repository.
2. **Framework Preset:** Other. Leave the build command and output directory empty.
3. Deploy.

It is a static site, so any static host works.

## Using a different RoomSense address

The pages point at `https://ar-furniture-liard.vercel.app`. To use another RoomSense deployment, replace that address in the `<script src=...>` line at the bottom of every page in `products/` (the home page has no RoomSense code). (The RoomSense repository generates these pages with `scripts/build-example-shop.ts` and `ROOMSENSE_URL=...`.)

Fictional store for a university project. No real orders. The 3D models are open-licence models credited inside the RoomSense viewer.
