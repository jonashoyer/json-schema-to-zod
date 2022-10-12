# json-schema-to-zod

Validate data with a JSON schema parsed to zod

### Limited JSON schema support!
Only a few types are currently supported
- `Array`
- `Object`
- `Enum`
- `String`, `Number`, `Integer`, `Boolean`

### Usage
```jsx
import { parseJsonSchema } from "json-schema-to-zod";

const jsonSchema = {
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "type": "object",
  "properties": {
    "productId": {
      "description": "The unique identifier for a product",
      "type": "integer"
    },
    "productName": {
      "description": "Name of the product",
      "type": "string"
    }
  },
  "required": [ "productId", "productName" ]
}

const zodSchema = parseJsonSchema(jsonSchema);
zodSchema.parse(data);

```
