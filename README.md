# BlueLeader
Automated Webpack Deployment to S3/CloudFront

## Installation
```
pip install BlueLeader
```

## Usage
```
BlueLeader [-h] (--production | --dev) config.json
```

## Sample Config

```json
{
    "region": "us-west-1",
    "webpack_config_template": "webpack-config.prod.js.template",
    "prod_destination_bucket": "myproject-static-assets",
    "dev_destination_bucket": "myproject-static-assets-dev",
    "destination_folder": "static",
    "local_static_folder": "./static/bundles/",
    "aws_profile": "my_profile"
}
```

## Overview

 * Generates a webpack config, setting the publicPath appropriately
 * Runs webpack on the generated config.
 * Uploads local static assets from 'local_static_folder' to 
  'destination_bucket'/'destination_folder'
 * Updates {bundle_url} in index.html to point to the generated bundle

## TODO

 * Cloudfront CDN support
