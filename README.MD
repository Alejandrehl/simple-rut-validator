# Simple Rut Validator

### How to use

1. `npm i simple-rut-validator`
2. `import { checkRut } from "simple-rut-validator"`

### Example

```javascript
import React, { useState, useEffect } from "react";
import { checkRut } from "simple-rut-validator";

const RegisterForm = () => {
  const [rut, setRut] = useState("");
  const [validRut, setValidRut] = useState(false);

  useEffect(() => {
    setValidRut(checkRut(rut));
  }, [rut]);

  return (
    <div>
      <input
        type="text"
        onChange={e => setRut(e.target.value)}
        placeholder="19123456-9"
        value={rut}
      />
      <label>
        {validRut
          ? "Rut ingresado es válido"
          : "Ingresa el rut sin puntos y con guión. Ejemplo: 19123456-9"}
      </label>
    </div>
  );
};

export default RegisterForm;
```
