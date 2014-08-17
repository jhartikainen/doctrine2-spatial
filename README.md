doctrine2-spatial
=================

Some spatial data related classes developed for Doctrine 2 to be used in www.wantlet.com

Implemented composer.json to allow for installation via composer.

Add the following to your composer.json

<pre><code>
{
    "require": { "Wantlet": "dev-master" },
    "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/jhartikainen/doctrine2-spatial",
            "comment": "Doctrine Spatial Data Types"
        }
    ]
}
</code></pre>

After installation, add this to you app/config/config.yml

<pre><code>
# Doctrine Configuration
doctrine:
    dbal:
        types:
            point:
                class:  Wantlet\ORM\PointType

    orm:
      auto_generate_proxy_classes: "%kernel.debug%"
      default_entity_manager:   default
      entity_managers:
          default:
              auto_mapping: true
              dql:
                numeric_functions:
                  DISTANCE: Wantlet\ORM\Distance
                  POINT_STR: Wantlet\ORM\PointStr

</code></pre>