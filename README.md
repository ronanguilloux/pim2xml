# Pim2XML


## Purpose

Create XML outputs out of XSD + [Akeneo PIM](https://github.com/akeneo) products.

This applies to any XML grammar, GS1 is just an example here.
Sample GS1 `xsd` files come from [https://github.com/oliot-tsd](https://github.com/oliot-tsd/tsd-heroku/tree/master/src/main/java/org/oliot/heroku/tsd/models/schema/tsd)


### What's done

- create PHP classes out of XSD

### Next step (not yet): 

- get families definitions out of [Akeneo Rest API](https://api.akeneo.com/)
- create an empty mapping configuration file, ready for starting manual mapping.
- map [Akeneo PIM Product families](https://help.akeneo.com/articles/what-is-a-family.html) to XSD
- Hint: use the JMS metadata file generated in var/metadata and just add a mapping information per (PIM product attribute to PHP object's property)
- get products data out of [Akeneo Rest API](https://api.akeneo.com/)
- loop over the products, generate XMLTypes, add mapped values on the fly
- generate final XML feed

## How it works

- conversions of XSD into PHP classes and JMS serializer definitions thanks to [goetas-webservices/xsd2php](https://github.com/goetas-webservices/xsd2php)

## Usage

First command available converts an XSD file into PHP classes and JMS serializer metadata files

```bash
bin/console convert var/config/ProductData.yml var/xsd/ProductData.xsd
```

## Output

- the `src/` contains the generated PHP classes
- the `var/metadata` contains the JMS metadata (yaml)
