Web assets (commit these):
  tabby-demo.web.mp4   — H.264, 1280px, ~3 MB
  tabby-demo.webm      — VP9, 1280px, ~3 MB
  tabby-demo-poster.jpg — first-frame poster

Source files (local only, gitignored):
  tabby-demo.mp4 — original screen recording
  tabby.gif      — not used on the site

Re-encode after updating the source recording:
  ffmpeg -y -i tabby-demo.mp4 -ss 1.5 -vframes 1 -update 1 -q:v 2 tabby-demo-poster.jpg
  ffmpeg -y -i tabby-demo.mp4 -an -vf "scale=1280:-2:flags=lanczos,fps=30" -c:v libx264 -preset medium -crf 24 -movflags +faststart -pix_fmt yuv420p tabby-demo.web.mp4
  ffmpeg -y -i tabby-demo.mp4 -an -vf "scale=1280:-2:flags=lanczos,fps=30" -c:v libvpx-vp9 -crf 32 -b:v 0 -row-mt 1 tabby-demo.webm
