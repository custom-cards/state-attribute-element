# State Attribute Element

This element is **not** all that useful as a card (it can be used for that to), the purpose of this is to give the option to add static text on a `picture-elements` card.

## Options

| Name | Type | Requirement | Description
| ---- | ---- | ------- | -----------
| type | string | **Required** | `custom:state-attribute-element`
| entity | string | **Required** | The entity_id of the entity you want to show.
| attribute | string | **Required** | The attribute of the entity you want to show.
| prefix | string | **Optional** | A string you want to show in front of the attribute, ex. "My prefix string: "
| suffix | string | **Optional** | A string you want to show after the attribute, ex. "My suffix string: "
| show_empty | boolean | **Optional** | Give you the possibility to show `unavailable` if the state is empty, default `false`

## Installation

### Step 1

Install `state-attribute-element` by copying `state-attribute-element.js`from this repo to `<config directory>/www/state-attribute-element.js` on your Home Assistant instanse.

**Example:**

```bash
wget https://raw.githubusercontent.com/custom-cards/state-attribute-element/master/state-attribute-element.js
mv state-attribute-element.js /config/www/
```

### Step 2

Link `state-attribute-element` inside you `ui-lovelace.yaml`.

```yaml
resources:
  - url: /local/state-attribute-element.js?v=0.3.0
    type: js
```

### Step 3

Add a custom element in your `ui-lovelace.yaml`

```yaml
      - type: picture-elements
        image: /local/files/LUfuf8ow.jpg
        elements:
          - type: custom:state-attribute-element
            entity: sensor.my_sensor
            attribute: my_attribute
            prefix: "My prefix string: "
```

## Example with styles

```yaml
      - type: picture-elements
        image: /local/files/LUfuf8ow.jpg
        elements:
          - type: custom:state-attribute-element
            entity: sensor.tautulli__ludeeus
            attribute: friendly_name
            prefix: "<b style='font-weigth: bold; color: red'>Friendle name: </b>"
            style:
              top: 47%
              left: 5px
              transform: none
```
![example](example.png)
