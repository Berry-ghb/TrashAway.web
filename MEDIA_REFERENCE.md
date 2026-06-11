# 📁 Media Files Reference

## Your Files in the Folder

```
TrashAway.web/
├── index.html          (Main website file)
├── video.mp4           ✅ Already in use
├── image.png           ✅ Ready to use (optional)
├── SETUP_GUIDE.md      (This documentation)
└── MEDIA_REFERENCE.md  (Quick reference)
```

---

## 🎥 Video (video.mp4) - CURRENTLY IN USE

### Where It's Used
**Location:** Hero section (top of page)
- **File path in code:** `src="video.mp4"`
- **Line number:** 1357
- **HTML element:** `<video class="hero-video" ...>`
- **Display:** Full-width background video
- **Auto-play:** Yes (muted)
- **Loop:** Yes
- **Fallback:** Shows solid gradient background if video fails

### Code Reference
```html
<!-- Line 1357 in index.html -->
<section id="hero">
  <div class="hero-overlay-fallback"></div>
  <div class="hero-particles" id="particles"></div>
  <video class="hero-video" autoplay muted playsinline loop preload="auto" id="hero-video">
    <source src="video.mp4" type="video/mp4">
  </video>
  <div class="hero-overlay"></div>
  <!-- Rest of hero content -->
</section>
```

### Video Specifications (Recommended)
- **Duration:** 10-30 seconds (will loop)
- **Resolution:** 1920×1080px minimum
- **File size:** < 3MB for fast loading
- **Format:** MP4 (H.264 codec)
- **Audio:** Muted (required)
- **Frame rate:** 24fps-30fps

---

## 🖼️ Logo (image.png) - OPTIONAL REPLACEMENT

### Current Logo Implementation
The logo is currently a **hardcoded SVG trash can icon** (not using image.png yet).

### Where Logos Appear in Code

#### 1️⃣ Navigation Bar Logo
- **Location:** Top-left corner of website
- **Line number:** 1340-1343
- **Element:** `.nav-logo-icon`
- **Current:** SVG trash can icon
- **Code:**
```html
<!-- Line 1340 -->
<a href="#" class="nav-logo">
  <div class="nav-logo-icon">
    <svg xmlns="..." viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
      <path stroke-linecap="round" stroke-linejoin="round" d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16"/>
    </svg>
  </div>
  <span class="nav-logo-text">Trash<span>Away</span></span>
</a>
```

#### 2️⃣ Footer Logo
- **Location:** Bottom-left of website
- **Line number:** 1449-1455
- **Element:** `.footer-logo`
- **Current:** SVG trash can icon
- **Code:**
```html
<!-- Line 1449 -->
<a href="#" class="footer-logo">
  <div class="footer-logo-icon">
    <svg xmlns="..." fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
      <path stroke-linecap="round" stroke-linejoin="round" d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16"/>
    </svg>
  </div>
  Trash<span>Away</span>
</a>
```

---

## 🔄 How to Replace Logo with image.png

### Option 1: Simple Image Replacement (Recommended)
Replace the SVG trash can in nav-logo-icon with your image:

**Find this code (Line ~1341):**
```html
<div class="nav-logo-icon">
  <svg xmlns="..." ...>
    <!-- SVG content here -->
  </svg>
</div>
```

**Replace with:**
```html
<div class="nav-logo-icon">
  <img src="image.png" alt="TrashAway" style="width: 100%; height: 100%; object-fit: cover;">
</div>
```

### Option 2: Large Hero Image
Add your image to the hero section:

**Add after line 1356 (before video):**
```html
<img src="image.png" alt="TrashAway" style="position: absolute; inset: 0; width: 100%; height: 100%; object-fit: cover; z-index: -1;">
```

### Option 3: Brand Section Image
Create a dedicated brand showcase section:

**Add before the footer (line ~1440):**
```html
<section class="section" style="text-align: center;">
  <img src="image.png" alt="TrashAway Brand" style="max-width: 400px; width: 100%; margin: 0 auto;">
</section>
```

---

## 📊 Image Specifications (Recommended)

If you replace the logo:
- **Format:** PNG (transparent background) or SVG
- **Dimensions:** 
  - Logo: 42×42px minimum (fits in nav icon)
  - Full size: 1920×1080px (for hero section)
- **File size:** < 500KB
- **Color scheme:** Match green theme (#00C853, #1B5E20)

---

## ⚡ Performance Tips

### For video.mp4
✅ Use a video compressor to reduce file size
✅ Keep duration under 30 seconds
✅ Use H.264 codec for best compatibility
✅ The site lazy-loads video (only plays when visible)

### For image.png
✅ Use PNG for transparency
✅ Use WebP format for better compression (fallback to PNG)
✅ Optimize with TinyPNG or similar tools
✅ Use CSS `object-fit: cover` for responsive sizing

---

## 🔗 Asset Loading Strategy

### Video Loading (Current Implementation)
```javascript
// Lazy loads video - only plays when visible on screen
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      vid.play().catch(() => vid.style.display = 'none');
      observer.unobserve(vid);
    }
  });
});
observer.observe(vid);
```

### Fallback Behavior
- **If video fails:** Shows solid gradient background (dark green to dark teal)
- **If image fails:** CSS background color shows instead
- **Mobile:** Video still works on mobile but may use cellular data

---

## 🚨 Troubleshooting

### Video Not Playing
1. Check file name matches: `video.mp4` (case-sensitive)
2. Verify file is in same folder as `index.html`
3. Check browser console for errors (F12)
4. Try different video format if needed

### Image Not Showing
1. Check file name matches: `image.png` (case-sensitive)
2. Verify PNG has transparent background
3. Check image dimensions (should be square for logo)
4. Verify it's in same folder as `index.html`

### Slow Loading
1. Compress video (target < 2MB)
2. Optimize image (target < 300KB)
3. Use modern formats (MP4 with H.264, WebP for images)
4. Check internet speed vs. file size

---

## 📱 Mobile Considerations

### Video on Mobile
- ✅ Plays automatically (muted only)
- ✅ Responsive sizing (fills screen)
- ⚠️ May use cellular data (users appreciate small file sizes)
- ⚠️ Some iOS versions require user interaction

### Logo on Mobile
- ✅ Scales responsively
- ✅ Visible in mobile nav
- ✅ Touch-friendly (44×44px minimum)

---

## 🎯 Quick Edit Guide

**To change video:**
1. Replace `video.mp4` file in folder
2. Restart browser
3. Done! (No code changes needed)

**To change logo:**
1. Replace SVG in nav (lines ~1340-1343)
2. Replace SVG in footer (lines ~1449-1455)
3. Or use image.png following Option 1 above

**To change both:**
1. Update both files in folder
2. Update both code locations
3. Test on desktop + mobile

---

## 📞 Need Help?

Refer to **SETUP_GUIDE.md** for:
- Complete enhancement details
- Color customization
- Animation speed adjustments
- Browser compatibility info
- Deployment instructions
