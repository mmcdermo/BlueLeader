# BlueLeader
Automated Webpack Deployment to S3/CloudFront

## Usage
```
deploy.py [-h] (--production | --dev) config.json
```

## Overview

 * Generates a webpack config, setting the publicPath appropriately
 * Runs webpack on the generated config.
 * Uploads local static assets from 'local_static_folder' to 
  'destination_bucket'/'destination_folder'
 * Updates {bundle_url} in index.html to point to the generated bundle

## TODO

 * Cloudfront CDN support
