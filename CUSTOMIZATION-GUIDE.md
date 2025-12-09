# 🎨 Customization Guide - Adding Your Own Images

This guide explains how to customize the Purple Hyacinth Cave theme with your own personal banner and cave images. These customizations are **optional** and should be added to your **local copy** of the CSS.

## ⚠️ Important Notes

- The main `purple-hyacinth-cave.css` file is designed to work universally without custom images
- Personal image customizations should be kept in **your own CSS** or at the end of the file
- Do not commit personal image URLs to the main theme file
- These customizations will only work on **your own profile**

## 🖼️ Adding Custom Banner Images

Banner images appear at the top of your den sections (Unsorted Lions, Nesting, Pride Overview).

### Step 1: Upload Your Images

Upload your banner images to an image hosting service that allows hotlinking, such as:
- PostImage (https://postimg.cc/)
- Imgur (https://imgur.com/)
- Imgbb (https://imgbb.com/)

Get the direct image URLs for each banner.

### Step 2: Add CSS for Banner Replacements

Add this CSS code **at the end** of your local copy of `purple-hyacinth-cave.css`:

```css
/* ==========================================
   PERSONAL BANNER CUSTOMIZATIONS
   Replace the URLs below with your own images
   ========================================== */

/* Hide original banner images */
img[src*="unsortedlionsbanner"],
img[src$="unsortedlionsbanner.png"],
img[src*="nestingbanner"],
img[src$="nestingbanner.png"],
img[src*="prideoverviewbanner"],
img[src$="prideoverviewbanner.png"] {
  opacity: 0 !important;
  visibility: visible !important;
  display: block !important;
}

/* Unsorted Lions Banner */
img[src*="unsortedlionsbanner"],
img[src$="unsortedlionsbanner.png"] {
  background-image: url('YOUR_UNSORTED_BANNER_URL_HERE') !important;
  background-repeat: no-repeat !important;
  background-position: center top !important;
  background-size: cover !important;
}

/* Nesting Banner */
img[src*="nestingbanner"],
img[src$="nestingbanner.png"] {
  background-image: url('YOUR_NESTING_BANNER_URL_HERE') !important;
  background-repeat: no-repeat !important;
  background-position: center top !important;
  background-size: cover !important;
}

/* Pride Overview Banner */
img[src*="prideoverviewbanner"],
img[src$="prideoverviewbanner.png"] {
  background-image: url('YOUR_PRIDE_OVERVIEW_BANNER_URL_HERE') !important;
  background-repeat: no-repeat !important;
  background-position: center top !important;
  background-size: cover !important;
}
```

### Step 3: Replace the URLs

Replace these placeholders with your actual image URLs:
- `YOUR_UNSORTED_BANNER_URL_HERE`
- `YOUR_NESTING_BANNER_URL_HERE`
- `YOUR_PRIDE_OVERVIEW_BANNER_URL_HERE`

**Example:**
```css
img[src*="unsortedlionsbanner"],
img[src$="unsortedlionsbanner.png"] {
  background-image: url('https://i.postimg.cc/XXXXXX/my-banner.jpg') !important;
  background-repeat: no-repeat !important;
  background-position: center top !important;
  background-size: cover !important;
}
```

## 🏔️ Adding Custom Cave Images

Cave images are the background images for your den caves.

### Step 1: Upload Your Cave Images

Upload your cave background images to an image hosting service (same as above).

### Step 2: Add CSS for Cave Replacements

Add this CSS code **at the end** of your local copy:

```css
/* ==========================================
   PERSONAL CAVE IMAGE CUSTOMIZATIONS
   Replace the URLs below with your own images
   ========================================== */

/* Generic cave default replacement (fallback) */
.cave-grid img[src*="cavedefault"],
.cave-grid img[src$="cavedefault.jpg"] {
  opacity: 0 !important;
  visibility: visible !important;
  display: block !important;
  background-image: url('YOUR_DEFAULT_CAVE_URL_HERE') !important;
  background-repeat: no-repeat !important;
  background-position: center top !important;
  background-size: cover !important;
}

/* Specific caves (if you have multiple caves) */
.cave-grid:nth-of-type(1) img[src*="cavedefault"] {
  background-image: url('YOUR_CAVE_1_URL_HERE') !important;
}

.cave-grid:nth-of-type(2) img[src*="cavedefault"] {
  background-image: url('YOUR_CAVE_2_URL_HERE') !important;
}

.cave-grid:nth-of-type(3) img[src*="cavedefault"] {
  background-image: url('YOUR_CAVE_3_URL_HERE') !important;
}

/* Add more caves as needed */
```

### Step 3: Replace the URLs

Replace the placeholder URLs with your actual cave image URLs.

## 🎯 Alternative Method: Using Cave Grid Backgrounds

Instead of replacing the `cavedefault.jpg` images, you can add backgrounds to the cave grid containers:

```css
/* Add background images to cave grids by link target */
a[href*="unsorted.php"] .cave-grid {
  background-image: url('YOUR_UNSORTED_CAVE_BG_URL') !important;
  background-repeat: no-repeat !important;
  background-position: center top !important;
  background-size: cover !important;
}

a[href*="nesting.php"] .cave-grid {
  background-image: url('YOUR_NESTING_CAVE_BG_URL') !important;
  background-repeat: no-repeat !important;
  background-position: center top !important;
  background-size: cover !important;
}

a[href*="lionoverview.php"] .cave-grid {
  background-image: url('YOUR_OVERVIEW_CAVE_BG_URL') !important;
  background-repeat: no-repeat !important;
  background-position: center top !important;
  background-size: cover !important;
}
```

## 📐 Image Size Recommendations

For best results, use images with these dimensions:

- **Banner Images**: 800-1200px wide, 150-250px tall
- **Cave Background Images**: 800-1200px wide, 400-600px tall
- **File Format**: JPG, PNG, or GIF (animated GIFs work!)
- **File Size**: Keep under 500KB for faster loading

## 🛠️ Tips & Tricks

1. **Test Your URLs**: Make sure your image URLs are direct links (ending in .jpg, .png, or .gif) and not page links
2. **Preview First**: Test your customizations in a browser before applying to your profile
3. **Keep Backups**: Save your customized CSS file locally before uploading
4. **Image Quality**: Use high-quality images that fit the purple hyacinth theme
5. **Transparency**: PNG images with transparency work great for layered effects

## 🔍 Troubleshooting

### Images Not Showing?
- Verify your image URLs are direct links
- Check that the hosting service allows hotlinking
- Make sure images are publicly accessible
- Clear your browser cache and refresh

### Images Look Stretched?
- Adjust `background-size` to `contain` instead of `cover`
- Use images with appropriate dimensions
- Try `background-position: center center` instead of `center top`

### Multiple Caves Not Working?
- Check the order of your caves on your profile
- The `:nth-of-type()` selector counts all elements of that type
- You may need to adjust the numbers (1, 2, 3...) based on your layout

## 💡 Example: Complete Personal Customization

Here's a complete example of personal customizations added at the end of your CSS:

```css
/* ==========================================
   MY PERSONAL CUSTOMIZATIONS
   ========================================== */

/* Unsorted Lions Banner */
img[src*="unsortedlionsbanner"],
img[src$="unsortedlionsbanner.png"] {
  opacity: 0 !important;
  visibility: visible !important;
  display: block !important;
  background-image: url('https://i.postimg.cc/XXXXX/my-unsorted-banner.jpg') !important;
  background-repeat: no-repeat !important;
  background-position: center top !important;
  background-size: cover !important;
}

/* Main Cave Background */
.cave-grid img[src*="cavedefault"],
.cave-grid img[src$="cavedefault.jpg"] {
  opacity: 0 !important;
  visibility: visible !important;
  display: block !important;
  background-image: url('https://i.postimg.cc/YYYYY/my-cave-bg.jpg') !important;
  background-repeat: no-repeat !important;
  background-position: center top !important;
  background-size: cover !important;
}
```

## ✨ Have Fun Customizing!

Remember: These customizations are for **your profile only**. The base Purple Hyacinth Cave theme works beautifully without any custom images!

---

*Questions? Check the main README.md or open an issue on the repository.*
