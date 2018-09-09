# Pim2XML


## Purpose

Create XML outputs out of XSD + [Akeneo PIM](https://github.com/akeneo) products.

This applies to any XML grammar, GS1 is just an example here.
Sample GS1 `xsd` files come from [https://github.com/oliot-tsd](https://github.com/oliot-tsd/tsd-heroku/tree/master/src/main/java/org/oliot/heroku/tsd/models/schema/tsd)


### What's done

- Create PHP classes out of XSD

### Next step (not yet): 

- map [Akeneo PIM Product families](https://help.akeneo.com/articles/what-is-a-family.html) to XSD
- then generate XML.

## How it works

* Conversions of XSD into PHP classes and JMS serializer definitions thanks to [goetas-webservices/xsd2php](https://github.com/goetas-webservices/xsd2php)

## Usage

First command available converts an XSD file into PHP classes and JMS serializer metadata filess

```bash
bin/console convert var/config/ProductData.yml var/xsd/ProductData.xsd
```

## Output

- the `src/` contains the generated PHP classes
- the `var/metadata` contains the JMS metadata (yaml)
