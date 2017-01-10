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

blue_leader.json:
```json
{
    "region": "us-west-1",
    "webpack_config_template": "webpack-config.template",
    "prod_destination_bucket": "myproject-static-assets",
    "dev_destination_bucket": "myproject-static-assets-dev",
    "destination_folder": "static",
    "local_static_folder": "./static/bundles/",
    "aws_profile": "my_profile"
}
```

webpack-config.template:
``` javascript
module.exports = {
    output: {
        publicPath: '{public_path}',
	...
    },
    ...
}
```

## Overview

 * Generates a webpack config, replacing {public_path} with the path to either
   an S3 bucket or CloudFront
 * Runs webpack on the generated config.
 * Uploads local static assets from 'local_static_folder' to 
  'destination_bucket'/'destination_folder'
 * Updates {bundle_url} in index.html to point to the generated bundle

## TODO

 * Cloudfront CDN support
