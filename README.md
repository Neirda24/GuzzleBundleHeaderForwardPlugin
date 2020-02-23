# Guzzle Bundle Header Forwarding Plugin

This plugin integrates a way to forward headers from the current symfony request into the cURL.


## Requirements
 - PHP 7.1 or above
 - [Guzzle Bundle][1]

 
### Installation
Using [composer][2]:

##### composer.json
``` json
{
    "require": {
        "neirda24/guzzle-bundle-header-forward-plugin": "^1.0"
    }
}
```

##### command line
``` bash
$ composer require neirda24/guzzle-bundle-header-forward-plugin
```

## Usage
### Enable bundle
``` php
# app/AppKernel.php

new EightPoints\Bundle\GuzzleBundle\EightPointsGuzzleBundle([
    new Neirda24\Bundle\GuzzleBundleHeaderForwardPlugin\GuzzleBundleHeaderForwardPlugin(),
])
```

### Basic configuration
``` yaml
# app/config/config.yml

eight_points_guzzle:
    clients:
        api_payment:
            base_url: "http://api.domain.tld"

            # define headers, options

            # plugin settings
            plugin:
                header_forward:
                    enabled: true
                    headers:
                        - 'Accept-Language'
```

[1]: https://github.com/8p/EightPointsGuzzleBundle
[2]: https://getcomposer.org/
