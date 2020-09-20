OCN XML Schema v1.0.0
===========

### What is it?
An XML schema is a description of a type of XML document, typically expressed in terms of constraints on the structure and content of documents of that type, above and beyond the basic syntactical constraints imposed by XML itself. - [Wikipedia - XML schema](https://en.wikipedia.org/wiki/XML_schema)

![Schema in Action!](https://i.imgur.com/fhjr7Q8.gif)

### How do I use it?

At the top of your XML within the `map` element add the following.

```
<map proto="1.4.3"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/harvanchik/PGMSchema/master/map.xsd">
```

This will allow you to run your XML through an online schema validator such as [FreeFormatter](https://www.freeformatter.com/xml-validator-xsd.html).

For live errors and suggestions we recommend using the [linter-autocomplete-jing](https://atom.io/packages/linter-autocomplete-jing) package within the [Atom Editor](https://atom.io/).

### How was it made?

This XML Schema was generated using all `map.xml`s within the [Overcast Network](https://gitlab.com/OvercastNetwork) repo of version 1.4 and higher. If something appeared within the XML of a loaded map it was presumed to be correct and a rule was created to accept such a thing.

However, some maps contained issues that were not picked up by PGM however still allowed it to be a "valid" XML, things such as spelling mistakes and out of place elements. Changes were made to resolve these issues however many may still be at large.

### What it can do?
- Suggest tags that are allowed within a module.
- Detect spelling mistakes within attributes and elements.
- List valid data types for specific attributes such as mob names and colors.

### What it can't do?
- Verification for in game aspects such as flag locations and regions.
- Naming errors for items, enchantments and potion effects etc (yet, support planned).
- Detect duplicate and incorrect usages of `ID`s such as teams, kits and filters.

### I've found an error!!
- As the `map.xsd` was created using maps within repo not all combinations of elements may be present.

If you find an issue where the XML is valid however the schema says otherwise feel free to make an issue or pull request so the error can be resolved.

- `x` module is not supported, it says it's invalid.

Some modules are also not included in the rules due to no maps within the repo using them (so they could not be genereated). Over time these newer modules will be added by hand.

- Older protocols are not working even though they work with PGM.

After `1.3.6` the overall naming scheme of XML was moved over to using IDs, this large change means older and newer maps would need a different schemas.
