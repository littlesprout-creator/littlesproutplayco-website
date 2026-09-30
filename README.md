# LittleSproutPlayCo. standalone website

This project recreates the public-facing LittleSproutPlayCo Shopify storefront as a standalone static website. The content and styling were pulled from the connected live Shopify store on September 30, 2026.

## Included
- Responsive homepage matching the current section order, palette, typography, hero, FAQ, newsletter and footer
- Shop collection with all 5 current products
- Dynamic product page with product galleries, descriptions, prices, inventory state and free loose-parts option where applicable
- About, Contact, Search and Cart
- LocalStorage-based cart (no account required)
- Checkout handoff page ready for Square or Stripe
- Cloudflare Pages `_headers` and `_redirects`

## Important before cancelling Shopify
The site currently uses your Shopify CDN URLs for the logo and product photos. This gives the closest possible visual copy right now, but it is not yet 100% independent of Shopify. Export/migrate those image files to your new hosting before closing Shopify, then replace the CDN URLs in `assets/products.js`, `assets/app.js`, `index.html`, `shop.html` and `about.html`.

## Checkout
The cart works, but payment is deliberately disabled until a payment processor is connected. Do not add raw card fields. Connect Square Payment Links/API or Stripe Checkout so payment happens on a PCI-compliant hosted checkout.

## Forms
- Contact currently opens the visitor's email app and addresses the message to the store contact email.
- Newsletter is visual only until an email service is connected.

## Legal pages
Shopify's full generated policy text was not exposed by the connected data source. Refund and shipping pages preserve the verified terms visible in the current store/FAQ; the privacy page is a starter. Review all three before launch.

## Deploy free on Cloudflare Pages
1. Create a free GitHub repository and upload the contents of this folder (not the ZIP itself).
2. In Cloudflare: Workers & Pages → Create → Pages → Connect to Git.
3. Choose the repository. For this static site, no build command is needed; the output directory is the repository root.
4. Deploy.
5. Add your custom domain in the Pages project's Custom domains section.

You can also deploy the folder by direct upload to any static host such as Cloudflare Pages, Netlify or GitHub Pages.
