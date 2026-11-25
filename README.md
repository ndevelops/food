# YASH Caterers — Visual Menu Website

**Live site:** https://capable-caramel-5a6bf8.netlify.app

A mobile-first, black-and-gold scrolling menu for YASH Caterers. Customers scroll down to play the opening video, then browse the menu images. It is a static site (plain HTML, CSS and JavaScript) with no build step and no framework.

## Scroll sequence

1. **Opening:** the supplied video plays as the visitor scrolls (first frame to last frame). "YASH Caterers" and "Good Food • Great Mood" fade in beside or below it.
2. **Veg Special:** full-width image.
3. **Non-Veg Special:** full-width image.
4. **More menu:** Starters, Ice-Cream, Sweets and Juices image, plus a small "Starter : Veg" card.
5. **Closing poster:** YASH Caterers poster with Call and WhatsApp buttons for both numbers.

## Files

```
index.html            the whole page (HTML + CSS + JS in one file)
assets/
  yash-video.mp4      opening video (original, unchanged)
  veg.jpg             Veg Special image (original)
  non-veg.jpg         Non-Veg Special image (original)
  more-menu.jpg       Starters / Ice-Cream / Sweets / Juices image (original)
  poster.jpg          closing YASH Caterers poster (original)
README.md             this file
```

All images and the video are the customer's original files. They are not cropped, recolored or edited. The page only adds a thin gold border and glow around them.

## Contact numbers

- 8828611354
- 7039675226

Each has a **Call** button (`tel:`) and a **WhatsApp** button (`https://wa.me/91<number>`, India country code +91).

## Updating the site

**Replace an image or the video:** save the new file with the same name inside `assets/` (for example a new `veg.jpg`) and redeploy.

**Change the menu text under an image:** the text on the menu images is part of the pictures, so you can't edit it in the code. Replace the image instead. The `alt="..."` text in `index.html` is only for screen readers and search engines. Update it to match any new image.

**Edit the Veg Starters card:** search `index.html` for `Starter : Veg` and edit the four `<li>` lines.

**Change a phone number:** search `index.html` for `8828611354` or `7039675226`. Update the visible number, the `tel:` link and the `wa.me/91...` link together.

**Change colors:** the gold shades are set in `:root { ... }` at the top of the `<style>` block (`--gold`, `--gold-hi`, `--gold-lo`).

## Deploying on Netlify

1. Open the site in the Netlify dashboard, go to **Deploys**, and drag the whole project folder (with `index.html` and `assets/` inside) onto the deploy area.
2. Or connect a Git repository: use no build command and set the publish directory to the project root.

Keep `index.html` at the top level and the `assets/` folder next to it, so the image and video paths keep working.

## Notes

- **Video scrubbing:** the video is controlled by scroll position. It needs a host that supports byte-range requests, which Netlify does. The video is muted and plays inline, as phones require.
- **Fonts:** Cinzel, Cormorant Garamond and Great Vibes load from Google Fonts. If they're blocked, the page falls back to the phone's default serif fonts.
- **Reduced motion:** visitors with "reduce motion" turned on in their device settings see the content without fade or slide animations.
- **Browsers:** it works in current Chrome, Safari, Firefox and Edge on phone and desktop.
