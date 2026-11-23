# PixelForge — Image & PDF Tools

A responsive, static website inspired by the general workflow of online image-resizing services. It is an original implementation and branding, not a copy of another site's code or assets.

## Included features

### Image tools
- Resize JPG/JPEG, PNG and browser-supported image formats by pixel dimensions.
- Optional aspect-ratio preservation.
- Export to JPG, PNG or WebP.
- Adjust lossy output quality for JPG/WebP.
- Process multiple images and download results individually or as a ZIP.

### PDF tools
- Compress PDF by rendering pages at a selected DPI and rebuilding the PDF.
- Export PDF pages to JPG or PNG.
- Combine multiple images into one PDF.
- Optional A4 or US Letter width for images-to-PDF output.

## Important PDF compression note

The PDF compressor uses rasterization. It can substantially reduce file size for image-heavy or scanned PDFs, but it flattens page content: selectable text, links, forms, accessibility structure, and vector sharpness are not preserved. Keep the original PDF. For lossless/object-level PDF optimization, a server-side tool such as Ghostscript or qpdf would be needed.

## Run locally

1. Extract the ZIP.
2. Open the `PixelForge` folder.
3. Double-click `index.html`, or run a local server:
   ```bash
   python -m http.server 8000
   ```
4. Visit `http://localhost:8000`.

The app loads PDF.js, pdf-lib, JSZip and fonts from public CDNs, so an internet connection is needed for those libraries. Your selected files are not uploaded by this app.

## Deploy publicly with Vercel

1. Create a new GitHub repository, for example `pixelforge-tools`.
2. Upload all files in this folder (keep `index.html`, `style.css`, `app.js`, `vercel.json`, and `README.md` at the repository root).
3. Sign in to Vercel and choose **Add New → Project**.
4. Import the GitHub repository.
5. Framework preset: **Other**. Build command: leave blank. Output directory: `.`.
6. Click **Deploy**. Vercel will provide a public HTTPS URL.
7. Test image resize, image conversion, PDF-to-image, images-to-PDF and PDF compression on desktop and mobile.

No database, API key, environment variable, login, or server is required for this starter version.

## Supported formats and limitations

- JPG/JPEG, PNG, WebP and other formats that the visitor's browser can decode are supported as image inputs.
- Output formats are JPG, PNG and WebP.
- HEIC/HEIF, TIFF, PSD, animated GIF preservation and RAW camera formats are not guaranteed. Browser support varies.
- Very large PDFs or images may use substantial device memory. Process smaller batches on phones or low-memory devices.
