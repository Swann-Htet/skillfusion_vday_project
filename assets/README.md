# Assets Documentation 📁

This folder contains all media assets for the Valentine's Day website. Follow these guidelines for optimal performance and compatibility.

## Folder Structure

```
assets/
├── images/
│   ├── 1.jpg - 9.jpg  ← Gallery photos for photos.html
│   └── p.jpg          ← Portrait for particle morphing (particle-image.html)
└── video/             ← Video files for video.html
```

---

## Images Folder (`images/`)

### Gallery Photos (1.jpg - 9.jpg)

**Used in:** `photos.html` - Interactive photo gallery

**Specifications:**
- **Format:** JPEG (.jpg) recommended for photos
- **Resolution:** Minimum 800px width, any aspect ratio
- **File Size:** 200KB - 2MB per image (balance quality vs. load time)
- **Quality:** 80-90% JPEG quality for optimal balance
- **Color:** RGB color space (not CMYK)

**Naming Convention:**
```
1.jpg  ← First gallery photo
2.jpg  ← Second gallery photo
3.jpg  ← Third gallery photo
...
9.jpg  ← Ninth gallery photo
```

**Customization:**
1. Replace existing numbered files with your photos
2. Maintain the numbered naming sequence (1.jpg, 2.jpg, etc.)
3. Keep filenames lowercase with no spaces
4. Crop photos to your preferred aspect ratio before uploading

**Recommended Editing:**
- **Brightness:** Slight increase for web viewing
- **Contrast:** Moderate boost for visual impact
- **Color:** Warm tones complement the romantic theme
- **Sharpening:** Light sharpening for web display

### Portrait Photo (p.jpg)

**Used in:** `particle-image.html` - Advanced particle morphing animation

**Specifications:**
- **Format:** JPEG (.jpg) or PNG (.png)
- **Resolution:** 512×512px minimum (square aspect ratio preferred)
- **File Size:** Under 2MB for optimal loading
- **Quality:** High contrast subjects work best
- **Background:** Simple, uncluttered backgrounds recommended

**Technical Requirements:**
- **High contrast:** Clear distinction between subject and background
- **Centered subject:** Face/main subject should be centered in frame
- **Good lighting:** Even lighting without harsh shadows
- **Minimal noise:** Low ISO/grain for clean particle generation

**Optimal Image Characteristics:**
```
✅ High contrast portrait
✅ Square or near-square aspect ratio
✅ Centered composition
✅ Clean, simple background
✅ Good lighting and sharpness

❌ Busy, cluttered backgrounds
❌ Low contrast/flat lighting
❌ Very wide or very tall aspect ratios
❌ Blurry or heavily compressed images
```

**Processing Tips:**
1. **Crop to square:** Use 1:1 aspect ratio
2. **Increase contrast:** Boost to ~20-30%
3. **Enhance lighting:** Avoid pure black/white areas
4. **Optimize file size:** Compress to 1-2MB maximum

---

## Video Folder (`video/`)

**Used in:** `video.html` - Video player with romantic styling

### Video Specifications

**Supported Formats:**
- **MP4** (recommended) - Best compatibility across browsers
- **WebM** - Alternative format for Firefox/Chrome
- **OGV** - Ogg Video format for additional compatibility

**Technical Requirements:**
- **Resolution:** 720p (1280×720) to 1080p (1920×1080)
- **Frame Rate:** 24fps, 30fps, or 60fps
- **Codec:** H.264 for MP4, VP8/VP9 for WebM
- **Duration:** Under 10 minutes recommended for web
- **File Size:** 50MB maximum per video

**Encoding Settings:**
```
Format: MP4
Video Codec: H.264
Audio Codec: AAC
Bitrate: 2-5 Mbps (depending on resolution)
Quality: High (but web-optimized)
Profile: Baseline or Main
```

### Video Optimization

**For Best Performance:**
1. **Compress for web:** Use tools like HandBrake or FFmpeg
2. **Add poster images:** Create poster.jpg for video previews
3. **Multiple formats:** Provide MP4 + WebM for best compatibility
4. **Optimize audio:** 128kbps AAC audio is sufficient

**Example FFmpeg Commands:**
```bash
# Convert to web-optimized MP4
ffmpeg -i input.mov -c:v libx264 -crf 23 -preset medium -c:a aac -b:a 128k output.mp4

# Create poster image from video
ffmpeg -i input.mp4 -ss 00:00:10 -vframes 1 poster.jpg
```

### Video Implementation

**Update video.html:**
```html
<video controls preload="metadata" poster="assets/video/poster.jpg">
  <source src="assets/video/your-video.mp4" type="video/mp4">
  <source src="assets/video/your-video.webm" type="video/webm">
  <p>Your browser doesn't support HTML5 video.</p>
</video>
```

---

## File Organization Best Practices

### Naming Conventions
- **Use lowercase:** Avoid uppercase letters in filenames
- **No spaces:** Use hyphens (-) or underscores (_) instead
- **Descriptive but concise:** `romantic-sunset.jpg` not `IMG_20240214_183045.JPG`
- **Version control:** Use numbered versions (v1, v2) if needed

### File Management
```
✅ Good Examples:
assets/images/wedding-photo.jpg
assets/video/proposal-moment.mp4
assets/images/first-date-1.jpg

❌ Avoid:
assets/images/IMG_1234.JPG
assets/video/VID 20240214 WA0001.mp4
assets/images/Photo From Sarah.jpeg
```

### Backup Strategy
1. **Keep originals:** Store full-resolution originals elsewhere
2. **Version control:** Use Git to track changes
3. **Multiple formats:** Keep both compressed and high-quality versions
4. **Cloud backup:** Store copies in cloud storage

---

## Performance Optimization

### Image Optimization Tools

**Recommended Tools:**
- **TinyPNG:** Online image compression
- **ImageOptim:** Mac image optimization
- **GIMP/Photoshop:** Manual editing and export
- **WebP conversion:** For modern browsers

**Batch Processing:**
```bash
# Using ImageMagick for batch resizing
mogrify -resize 1200x800> -quality 85 *.jpg

# Convert to WebP format
for file in *.jpg; do
  cwebp -q 85 "$file" -o "${file%.jpg}.webp"
done
```

### Loading Performance

**Lazy Loading (Future Enhancement):**
```html
<!-- Add loading="lazy" for modern browsers -->
<img src="assets/images/1.jpg" loading="lazy" alt="Gallery photo">
```

**Progressive JPEG:**
- Enable progressive encoding when saving JPEGs
- Provides better perceived loading performance
- Supported by most image editors

### Mobile Optimization
- **Responsive images:** Consider different sizes for mobile
- **Touch-friendly:** Ensure videos work with touch controls
- **Data awareness:** Provide options for lower quality on slow connections

---

## Troubleshooting

### Common Issues

**Images Not Loading:**
1. Check file paths match exactly (case-sensitive on some servers)
2. Verify file permissions (readable by web server)
3. Confirm file formats are supported
4. Check for special characters in filenames

**Videos Not Playing:**
1. Test in multiple browsers
2. Verify codec compatibility
3. Check file size limits (some hosting has restrictions)
4. Ensure proper MIME types are set

**Performance Problems:**
1. Compress images further
2. Use WebP format where supported
3. Implement lazy loading
4. Consider CDN for large files

### File Size Guidelines

**Target Sizes for Web:**
```
Gallery Images:    200KB - 1MB each
Portrait (p.jpg):  500KB - 2MB
Videos:           10MB - 50MB each
Total Assets:     Under 100MB for all files
```

### Quality Testing

**Before Going Live:**
- [ ] All images load quickly (under 3 seconds)
- [ ] Videos play smoothly without buffering
- [ ] Particle-image.html loads p.jpg without CORS errors
- [ ] Gallery photos display correctly in all browsers
- [ ] Mobile performance is acceptable
- [ ] File sizes are optimized for web delivery

---

For technical implementation details, see [docs/FEATURES.md](../docs/FEATURES.md).
For page-specific usage information, see [docs/PAGES.md](../docs/PAGES.md).