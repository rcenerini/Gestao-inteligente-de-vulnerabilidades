---
name: package-frontend-app
description: Package and build React frontend for production deployment
trigger: "Package frontend for production"
---

# Package Frontend Application

## Steps

1. **Prepare Build Environment**
   ```bash
   npm ci
   npm run lint
   npm run type-check
   ```

2. **Build React Application**
   ```bash
   npm run build
   ```
   - Minify and bundle all assets
   - Generate source maps for debugging
   - Create static assets directory

3. **Optimize Assets**
   - Image compression (WebP format)
   - Code splitting by route
   - Tree shaking for unused code
   - CSS minification

4. **Configure Static Hosting**
   - Upload dist/ to S3 bucket
   - Setup CloudFront CDN
   - Configure cache headers
   - Enable gzip compression

5. **Generate Build Artifacts**
   - Build manifest (file hashes)
   - Asset inventory
   - Performance metrics
   - Bundle analysis report

6. **Validate Production Build**
   ```bash
   npm run test:prod
   npm run test:performance
   ```

## Success Criteria
- Build completes without errors
- Bundle size < 500KB (gzipped)
- All assets uploaded to S3/CDN
- Performance audit score ≥ 90
- Accessibility audit passes
