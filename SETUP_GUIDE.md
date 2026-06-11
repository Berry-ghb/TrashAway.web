# TrashAway Website - Setup Guide

## 📁 File Locations & Usage

### Video (video.mp4)
**Location in code:** Line ~1357 in `index.html`
```html
<video class="hero-video" autoplay muted playsinline loop preload="auto" id="hero-video">
  <source src="video.mp4" type="video/mp4">
</video>
```
- **Where it appears:** Hero section (full-screen background)
- **Format:** MP4 video
- **Optimal specs:** 1920x1080px, 10-15 seconds, looped, muted
- **Performance:** Video is lazy-loaded and only plays when visible

### Logo/Images (image.png)
The logo is currently **hardcoded as an SVG** in the navigation and footer:
- **Navigation logo:** Line ~1342 (trash can icon)
- **Footer logo:** Line ~1446 (trash can icon)

If you want to replace the SVG trash can icon with your image.png:

**Option 1: Use as brand logo in navbar**
Replace the SVG in `.nav-logo-icon` section with:
```html
<img src="image.png" alt="TrashAway" style="width: 42px; height: 42px;">
```

**Option 2: Use as brand image elsewhere**
Add to any section with:
```html
<img src="image.png" alt="Description" style="max-width: 100%;">
```

---

## ✨ Recent Enhancements

### 1. **Removed Signup Options**
- ❌ "Get Started" → ✅ "Get The App"
- ❌ "Create Free Account" → ✅ "Get The App Now"
- ❌ "Subscribe Now" → ✅ "Get The App"
- ❌ "Sign Up as Collector" → ✅ "Get The App"

All buttons now redirect to the contact/CTA section.

### 2. **Enhanced Interactivity**
✅ **3D Card Tilt Effects**
- Feature cards tilt 3D on mouse movement (perspective: 1200px)
- Team cards have enhanced 3D rotation
- Step items respond to cursor position
- Value items skew and slide on hover

✅ **Button Proximity Detection**
- Buttons react to cursor proximity (within 150px)
- Buttons predict user movement and move toward cursor
- Smooth magnetic effect for better engagement

✅ **Cursor Enhancements**
- Custom cursor scales to 2x on interactive elements
- Dynamic cursor color changes
- Smooth cursor trailing animation (0.18s damping)

✅ **Scroll Animations**
- Reveal animations on scroll with 0.8s duration
- Staggered animations for list items
- Parallax effects support (via data-parallax attribute)
- Smooth scroll behavior

### 3. **Performance Optimizations**
- 🚀 Lazy-load video (only plays when visible)
- 🎯 Optimized scroll events with requestAnimationFrame
- ⚡ Passive event listeners for better performance
- 🔄 Debounced proximity detection (16ms intervals)
- 📱 Reduced motion support (prefers-reduced-motion)
- 🎨 Dark mode media query support

### 4. **Mobile Improvements**
- ✅ Touch-friendly hover states
- ✅ Body scroll lock when mobile menu opens
- ✅ Better responsive animations
- ✅ Optimized for smaller screens
- ✅ Removed heavy 3D effects on touch devices

### 5. **New CSS Features**
- Added `.stagger-item` for sequential animations
- Enhanced `.reveal` animations with better easing
- Button ripple effect on hover (::before pseudo-element)
- Improved card shadow and glow effects
- Better transition timing (cubic-bezier)

---

## 🎨 Color Theme

The website uses an eco-friendly green color scheme:
```css
--g: #00C853          /* Main green */
--g2: #00E676         /* Bright green */
--g3: #1B5E20         /* Dark green */
--glow: rgba(0,200,83,0.3)  /* Glow effect */
```

---

## 📞 Call-to-Action Links

All CTA buttons now direct to:
- Primary CTA: `#contact` (bottom CTA band)
- Secondary: `#how-it-works` (explainer section)
- Pricing: `#pricing` (pricing section)

---

## 🚀 How to Deploy

1. **Replace assets:**
   - Keep `video.mp4` in root folder
   - Keep `image.png` in root folder for logo replacement

2. **Update video source (if needed):**
   Edit line 1357 in index.html:
   ```html
   <source src="your-video.mp4" type="video/mp4">
   ```

3. **Replace logo (optional):**
   Edit `.nav-logo-icon` SVG with your image

4. **Test on multiple devices:**
   - Desktop (Chrome, Firefox, Safari)
   - Mobile (iOS Safari, Chrome Mobile)
   - Tablet (iPad, Android tablets)

5. **Performance check:**
   - Video should load quickly (< 3MB ideally)
   - Image should be optimized (< 500KB)
   - Test scroll performance on slower devices

---

## 🔧 Browser Support

✅ Chrome 90+
✅ Firefox 88+
✅ Safari 14+
✅ Edge 90+
✅ Mobile browsers (iOS 13+, Android 5+)

---

## 💡 Customization Tips

### Change Button Colors
Find in CSS (around line 70):
```css
.btn-green {
  background: var(--g);  /* Change this color */
}
```

### Adjust Animation Speed
- Scroll reveals: Change `0.8s` in `.reveal` class (line ~920)
- Cursor tracking: Change `0.18` in cursor animation (line ~1466)
- Proximity detection: Change `150` in distance calculation (line ~1575)

### Modify 3D Tilt Effect
- Card tilt intensity: Change `8}deg` to different value (line ~1552)
- Team card tilt: Change `10}deg` to different value (line ~1577)

---

## 📱 Mobile-Specific Features

- Buttons won't hover on touch devices (media query: `hover: none`)
- Reduced animation on devices with `prefers-reduced-motion`
- Touch-friendly spacing and sizing
- Optimized mobile menu with scroll lock

---

Created: 2024
Updated with: 3D interactions, proximity detection, performance optimizations
